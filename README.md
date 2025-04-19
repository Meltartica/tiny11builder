# Tiny11 Builder (GitHub Actions)

> [!NOTE]
> The original README can be accessed from the [link](https://github.com/ntdevlabs/tiny11builder/blob/main/README.md).

## Instructions
1. Fork this repository.
2. Download Windows 11 from the [Microsoft Website](https://www.microsoft.com/en-us/software-download/windows11).
   - Select your device architecture (x64 or Arm64).
   - Select the language of your choice (e.g., English).
   - Right-click the `Download button` and press `Copy Link Address`.
3. Go to the `Actions` tab and select `Build Tiny11 ISO` workflow.
4. Press the `Run workflow` button.
   - Select `ISO Image Edition` (e.g., 1 for Home, 6 for Pro)
   - Provide your ISO Image URL (leave blank for default 24H2 Image)
   - Provide list of package prefixes to keep (e.g., Microsoft.Paint_,Microsoft.People_)
8. Sit back and relax :)
9. When the image is done building, press the workflow run `Build Tiny11 ISO` and download the Artifact named `tiny11-iso`.

## Removed Pre-Installed Applications

| Application | Package Name | Description |
|-------------|--------------|-------------|
| Clipchamp | `Clipchamp.Clipchamp_` | Video editing software |
| Bing News | `Microsoft.BingNews_` | News aggregator |
| Bing Search | `Microsoft.BingSearch_` | Search engine |
| Bing Weather | `Microsoft.BingWeather_` | Weather application |
| Xbox Game Bar | `Microsoft.GamingApp_` | Gaming overlay and tools |
| Get Help | `Microsoft.GetHelp_` | Windows support application |
| Get Started | `Microsoft.Getstarted_` | Windows onboarding app |
| Microsoft Office Hub | `Microsoft.MicrosoftOfficeHub_` | Office application hub |
| Microsoft Solitaire Collection | `Microsoft.MicrosoftSolitaireCollection_` | Collection of solitaire games |
| Outlook | `Microsoft.OutlookForWindows_` | Email and calendar application |
| Paint | `Microsoft.Paint_` | Image editing application |
| People | `Microsoft.People_` | Contacts management |
| Power Automate Desktop | `Microsoft.PowerAutomateDesktop_` | Automation tool |
| Sticky Notes | `Microsoft.MicrosoftStickyNotes_` | Digital sticky notes |
| Microsoft To Do | `Microsoft.Todos_` | Task management application |
| Photos | `Microsoft.Windows.Photos_` | Photo viewing and editing |
| Alarms & Clock | `Microsoft.WindowsAlarms_` | Alarm and timer application |
| Calculator | `Microsoft.WindowsCalculator_` | Calculator application |
| Camera | `Microsoft.WindowsCamera_` | Camera application |
| Mail & Calendar | `microsoft.windowscommunicationsapps_` | Email and calendar (replaced by Outlook) |
| Feedback Hub | `Microsoft.WindowsFeedbackHub_` | Windows feedback tool |
| Maps | `Microsoft.WindowsMaps_` | Mapping application |
| Notepad | `Microsoft.WindowsNotepad_` | Text editor |
| Voice Recorder | `Microsoft.WindowsSoundRecorder_` | Audio recording application |
| Xbox Console Companion | `Microsoft.Xbox.TCUI_` | Xbox companion application |
| Xbox Game Bar | `Microsoft.XboxGamingOverlay_` | Gaming overlay |
| Xbox Game Bar | `Microsoft.XboxGameOverlay_` | Gaming overlay (alternative) |
| Xbox Speech to Text | `Microsoft.XboxSpeechToTextOverlay_` | Speech recognition for gaming |
| Your Phone | `Microsoft.YourPhone_` | Phone linking application |
| Groove Music | `Microsoft.ZuneMusic_` | Music player (legacy) |
| Movies & TV | `Microsoft.ZuneVideo_` | Video player (Netflix-Like) |
| Microsoft Family | `MicrosoftCorporationII.MicrosoftFamily_` | Family safety features |
| Quick Assist | `MicrosoftCorporationII.QuickAssist_` | Remote assistance tool |
| Microsoft Teams | `MicrosoftTeams_` | Collaboration and communication platform |
| Cortana | `Microsoft.549981C3F5F10_` | Digital assistant |
| Microsoft Teams | `MSTeams_` | Microsoft Teams application |
| Windows Web Experience | `MicrosoftWindows.Client.WebExperience_` | Web integration features |
| Dev Home | `Microsoft.Windows.DevHome_` | Developer tools hub |

## Optional Installation
1. After setup and connected to the internet, it is recommended to install the package manager from Microsoft called `WinGet`. Run this command in PowerShell:
```
Add-AppxPackage -RegisterByFamilyName -MainPackage Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```

## Known issues
1. Microsoft Edge is removed, but remnants can be found in Settings (App itself is deleted).
   - You can install any browser using `WinGet` (update first using Microsoft Store or PowerShell).
```
winget install Mozilla.Firefox
winget install Opera.Opera
winget install Google.Chrome
```
   - To use Edge, Copilot, and Web Search, install Edge using Winget: `winget install edge`.
2. Outlook and Dev Home might reappear after some time.
3. If building on `arm64` architecture, a glimpse of an error can be seen while running the script.
   - The `arm64` image doesn't have OneDriveSetup.exe included in the System32 folder.
4. There are some errors, like `The system was unable to find the specified registry key or value.` or `The system cannot find the path specified.`.

## Features to be implemented
- More ad suppression

## Credits
- [NTDEV](https://github.com/ntdevlabs) and other contributors for making this amazing script.
- [adrijanh9](https://github.com/adrijanh9) for updated [services](https://github.com/ntdevlabs/tiny11builder/pull/273) and [software](https://github.com/ntdevlabs/tiny11builder/pull/253) to remove.
- [altship](https://github.com/altship) for [fixing 24H2 services deletion](https://github.com/ntdevlabs/tiny11builder/pull/289).
- [Snshadow](https://github.com/Snshadow) for [fixing with oscdimg.exe search, ExecutionPolicy, etc](https://github.com/ntdevlabs/tiny11builder/pull/319/commits).
- [MaykGyver](https://github.com/MaykGyver) for [the updated software list to remove](https://github.com/ntdevlabs/tiny11builder/pull/324).
- [Miiraak](https://github.com/Miiraak) for [adding SKU validation](https://github.com/ntdevlabs/tiny11builder/pull/338).
