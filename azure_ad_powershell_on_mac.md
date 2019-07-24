# Azure PowerShell on MacOS #

Simple instructions on how to get started with the Azure AD PowerShell module on Mac. Most of this works on PowerShell core 6 on Windows as well.

On the Mac terminal:

```bash
# install powershell from homebrew
brew cask install powershell
# Start powershell
pwsh
```

On the PowerShell:

Notice that the PowerShell commands support tab completion.

```powershell
# Install the Azure AD module
Install-Module -Name Az -AllowClobber
# Enable credential autosaving (you don't need to log in to azure on every new window)
Enable-AzContextAutosave
# Connect to your Azure AD account
Connect-AzAccount

# Get available AD tenants
Get-AzTenant
# Get available subscriptions
Get-AzSubscription

# Context is a container for login credentials, like username, Azure AD tenant and subscription. So th set the Context to which your commands affect, use the following commands

# List the different Contexts you have
Get-AzContext -ListAvailable
# Show the currently active context
Get-AzContext
# Select default context
Select-AzContext ITTeam
# Select context for the current window
Select-AzContext ITTeam -Scope Process
```
