---
title: Collect File operation in Defender portal (MDE/XDR) not displaying file collected
date: 2025-08-08 00:00:00 +/-TTTT
categories: 
tags:      # TAG names should always be lowercase
description: Workaround to the limitation of the Defender portal not being able to display which file was collected through the "Collect File" action.
author: mtjBeryl
---

Defender portal is currently limited and does not display the file that was collected with the "Collect File" action, on the Action Center. Here we track *SenseSampleUploader.exe* execution command line through the machine logs to retrieve the missing information from the portal (trimmed):

`upload"C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Temp\SampleCache\59C6.tmp" https://wseu1westprod.blob.core.windows.net/20250808/sha1/0bdfed9e82dc420f5357b829522e5c3765667ff4/a2dae0bb5da85a8db791a5d0233ef42c.zip?sv=2019-07-07&sr=b&sig=…”`

Correlating the Action End Time (time when the file was uploaded to the Defender backend) with the execution logs of *SenseSampleUploader.exe* (as a child of *MsSense.exe*) **on the machine where the collection was performed**, we're able to get the SHA1 of the file that was requested for collection: `/sha1/0bcfed9e82dc420f5357b829522e5b3765667ff4`.

With this, you can then do a quick KQL lookup to audit your activities:

```
DeviceProcessEvents
| where FileName =~ "SenseSampleUploader.exe"
| where ProcessCommandLine contains "sha1"
| extend SHA1_ext = extract(@"\/sha1\/([a-fA-F0-9]{40})", 1, ProcessCommandLine)
| join DeviceFileEvents on $left.SHA1_ext==$right.SHA1
| summarize FileSeenOnDevices=make_set(DeviceName1) by Timestamp, ExtractedFrom=DeviceName, FileName1, SHA11
```
