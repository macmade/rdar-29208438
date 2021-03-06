rdar://29208438
===============

![Status](https://img.shields.io/badge/status-duplicate-lightgray.svg?style=flat)
[![Radar](https://img.shields.io/badge/rdar-29208438-blue.svg?style=flat)]
(http://openradar.appspot.com/radar?id=4976964230184960)
[![Contact](https://img.shields.io/badge/contact-@macmade-blue.svg?style=flat)](https://twitter.com/macmade)  
[![Donate-Patreon](https://img.shields.io/badge/donate-patreon-yellow.svg?style=flat)](https://patreon.com/macmade)
[![Donate-Gratipay](https://img.shields.io/badge/donate-gratipay-yellow.svg?style=flat)](https://www.gratipay.com/macmade)
[![Donate-Paypal](https://img.shields.io/badge/donate-paypal-yellow.svg?style=flat)](https://paypal.me/xslabs)

Xcode - Breakpoints don't work with incremental LTO
---------------------------------------------------

 - State: Duplicate (closed)
 - Product: Developer Tools
 - Rank: No Value
 - Date: 11-Nov-2016 00:13 AM

### Status

**Duplicate of 28529594 (closed)**

> Engineering has determined that your bug report is a duplicate of another issue and will be closed. 
> 
> The open or closed status of the original bug report your issue was duplicated to appears in the yellow "Duplicate of XXXXXXXX" section of the bug reporter user interface. This section appears near the top of the right column's bug detail view just under the bug number, title, state, product and rank.
> 
> If you have any questions or concerns, please update your report directly here: http://bugreport.apple.com/.

### Summary

When using incremental link-time optimisation in Xcode, breakpoints won’t trigger...

The program will execute as if no breakpoints were set.

This only happen when LTO is set to incremental.  
Targets without LTO or with the old monolithic LTO are not affected.

This is always reproductible, no matter which language is used.

### Steps to Reproduce
Attached is an example Xcode project which demonstrates the issue.

It only consist of a `main.m` file, with a _“hello, world”_.

Try putting a breakpoint somewhere in the `main` function.

Now there’re two schemes you need to test:

 - `LTO` - **With link-time optimisation.**  
   Breakpoint won’t trigger.
 - `NO-LTO` - **Without link-time optimisation.**
   Breakpoint will be hit as expected.

### Expected Results

The breakpoint should be hit with both schemes.

### Actual Results

Breakpoint is not hit when using the scheme with incremental LTO.

### Version

 - macOS Sierra 10.12.2 Beta (16C41B)
 - Xcode version 8.1 (8B62)

_Note that the issue is also reproductible with Xcode version 8.2 beta (8C23)_

### Configuration

The issue always occurs when using incremental LTO.

Repository Infos
----------------

    Owner:			Jean-David Gadina - XS-Labs
    Web:			www.xs-labs.com
    Blog:			www.noxeos.com
    Twitter:		@macmade
    GitHub:			github.com/macmade
    LinkedIn:		ch.linkedin.com/in/macmade/
    StackOverflow:	stackoverflow.com/users/182676/macmade
