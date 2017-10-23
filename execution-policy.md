# How do I fix "the execution of scripts is disabled on this system" errors?

On Windows desktops and older versions of Windows Server, not only is the `.ps1` extension not associated with PowerShell, PowerShell scripts are not enabled by default. In order to run scripts, you must first run `Set-ExecutionPolicy RemoteSigned`.  If you're not the administrator of the machine, you may need to add the `-Scope CurrentUser` option. For more information, read the help: `Get-Help Set-ExecutionPolicy -Online`.

* [Set-ExecutionPolicy](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy)
* [About Execution Policies](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies)