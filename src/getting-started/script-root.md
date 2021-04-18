# How do I determine the location of the current PowerShell script?

Ever since PowerShell 3, there is an automatic variable `$PSScriptRoot` which is set to the path of the directory that contains the currently-executing module or script. Additionally, there is `$PSCommandPath` which contains the path (including the file name) to the currently executing script.

