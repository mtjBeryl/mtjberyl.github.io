---
title: HackTheBox Academy white theme using Stylus browser extension
date: 2025-08-25 00:00:00 +/-TTTT
categories: 
tags:      # TAG names should always be lowercase
description: Workaround to the idea that cybersecurity is all about dark themes.
author: mtjBeryl
---

Just load up Stylus or any other browser extension that allows you to customize the CSS for a web page and use the below CSS to convert your HTB Academy dark theme into a white theme. Probably there could be some improvements, but it works for me.

`@-moz-document domain("academy.hackthebox.com") {
    /* Base Styling */
    .col-md-12.col-xl-9.col-xxl-7, 
    pre.language-shell-session, 
    .card-body.bg-color-blue-nav, 
    .card-body, 
    label.module-question, 
    span.badge.badge-soft-dark.font-size-14.mr-2, 
    .custom-styling, 
    body, 
    h2, 
    h5, 
    h6, 
    .my-3.p-3.vpn-switch-card, 
    p.font-size-14.color-white.mb-0 {
        background-color: #fff; /* Softer light gray background */
        color: #2f2f2f; /* Dark gray text for contrast */
        font-family: "Arial";
        text-rendering: optimizeLegibility;
        line-height: 1.6;
    }
    #walkthroughModal .modal-content
         {
            background-color: #fff !important;
        }
    
    .card-title-desc{
        color: #111;
    }
    
    body{
        font-family: Arial,Helvetica,sans-serif;
        background-color: #fff;
    }

    /* Main Content Background and Borders */
    .card, .streak-card {
        background-color: #ffffff; /* Light background for card areas */
        border: 1px solid #e0e0e0; /* Light gray border for separation */
        border-radius: 8px; /* Rounded corners */
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Subtle shadow for depth */
        padding: 20px;
    }

    /* Text */
    .text-left {
        color: #1f1f1f;
        font-family: "Arial";
    }

    /* Font Styling */
    .training-module, .training-module p, .training-module tr td, .training-module li {
        font-family: "Arial";
        text-rendering: optimizeLegibility;
    }

    /* Buttons */
    .btn-lighter {
        background-color: #e8e8e8; /* Light gray for soft contrast */
        color: #2f2f2f;
        border-radius: 5px;
        padding: 8px 12px;
    }
    .btn-lighter:hover {
        background-color: #d0d0d0; /* Darker gray on hover */
    }
    
    /* Headings */
    .h1, .h2, .h3, .h4, .h5, .h6, h1, h2, h3, h4, h5, h6 {
        color: #0f0f0f;
        font-family: "Arial";
        margin-top: 20px;
        margin-bottom: 10px;
    }

    /* Code Blocks */
    code[class*="language-"], pre[class*="language-"] {
        font-family: "Courier New", monospace;
        padding: 4px 6px;
        border-radius: 4px;
        font-size: 0.95em;
        color: #eee;
    }
    code.language-powershell-session {
        color: white;
    }
    pre[class*="language-"] {
        padding: 12px;
        border: 1px solid #e0e0e0;
        overflow-x: auto;
    }
    code {
        color: #990000; /* Dark red for inline code */
    }

    /* Powershell session override */
    code.language-powershell-session {
        color: black !important;
    }

    /* Links */
    a {
        color: #0056b3; /* Softer blue */
        text-decoration: none;
        font-weight: 600;
    }
    a:hover {
        color: #004080; /* Darker blue on hover */
        text-decoration: underline;
    }
    code[class*=language-shell], pre[class*=language-shell] {
        color: #c4c4c4;
    }
    code[class*=language-shell-session], pre[class*=language-shell-session] {
        color: #363636;
    }


    /* Tables */
    .table {
        color: #1f1f1f;
        font-family: "Arial";
        background-color: #f9f9f9;
        border: 1px solid #ddd;
    }
    .table th, .table td {
        padding: 12px;
        border-top: 1px solid #ddd;
    }

    /* Other Elements */
    .training-module .module-question {
        color: #2f2f2f;
    }
    .streak-card {
        background-color: #fff;
    }

    /* Additional Layout and Padding */
    .content-block {
        padding: 20px;
        margin-bottom: 20px;
        background-color: #ffffff;
        border-radius: 8px;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }
}
`
