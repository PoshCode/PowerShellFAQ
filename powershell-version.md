# How do I determine the current version of PowerShell?

The version of PowerShell is always available within PowerShell in the `$PSVersionTable` as the "PSVersion" property. As of PowerShell 5, there is also a "PSEdition" property (which is also available as it's own `$PSEdition` variable) to distinguish Windows PowerShell (the "Desktop" edition) from PowerShell Core (the "Core" edition).