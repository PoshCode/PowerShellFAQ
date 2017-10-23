# How do I set the PATH in PowerShell?

The PATH, like all environment variables, is accessible in PowerShell via the `Env` drive, and you can set it using variable syntax, like: `$Env:PATH += ";$pwd"` to add the present working directory to it. In Windows, the directory separator for the path is ";", but on Linux it's ":" -- to be safe, you can use `[IO.Path]::PathSeparator` like this: `$Env:Path += [IO.Path]::PathSeparator + $pwd`

Note that += is the "append" operator for strings.

To make changes permanent you can either put them in a profile script (which is cross-platform), or if you need the changes to affect apps outside PowerShell on Windows, you can force them into the environment storage using `[Environment]::SetEnvironmentVariable` -- but you must be careful, in this case, not to put your personal environment into the machine's environment. Here's a simple two-line script that will add a path to the PATH environment variable for all users in Windows:

```posh
function Add-Path($Path) {
    $Path = [Environment]::GetEnvironmentVariable("PATH", "Machine") + [IO.Path]::PathSeparator + $Path
    [Environment]::SetEnvironmentVariable( "Path", $Path, "Machine" )
}
```