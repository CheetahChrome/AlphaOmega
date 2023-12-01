---
title: Oh My Posh Powershell Notes
layout: default
---  
  
Here are my raw notes to get Oh-My-Posh working with Terminal and Powershell.  
  
- `Set-ExecutionPolicy RemoteSigned`
- `winget install Microsoft.WindowsTerminal`
- `winget install oh-my-posh`
- `Install-Module posh-git -Scope CurrentUser`
- Install [Nerd Fonts](https://www.nerdfonts.com/font-downloads)
- `Test-Path $Profile`
- `New-Item -Path $Profile -Type File -Force`
- `Notepad $Profile`
    - Add 
```Powershell  
Import-Module -Name Terminal-Icons  
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\paradox.omp.json" | Invoke-Expression 
```
- Terminal->Settings->Defaults->Appearance set to `CaskaydiaCove Nerd Font`
- Open new powershell window.

----  
{: .warning }
If when doing a `dir` or `gci` and seeing boxes for the Terminal-Icons you may need to unstall Terminal or update the nerd fonts.
----    
  
See [How to Set up the Windows terminal with Powershell and Oh My Posh - DEV Community](https://dev.to/slydragonn/how-to-set-up-the-windows-terminal-with-powershell-and-oh-my-posh-2ba4#:~:text=How%20to%20Set%20up%20the%20Windows%20terminal%20with,...%206%206.%20Set%20up%20the%20terminal%20background) for a more graphical rep.
  
Note if a `gci` or `dir` 