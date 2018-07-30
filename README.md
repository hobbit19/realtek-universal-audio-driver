# Realtek Universal Audio Driver (UAD)

## Download

### Universal Audio Driver

https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/Realtek

### Setup Program for UAD

https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/XSetup

### Third Party

* A-Volute: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/A-Volute

* Dolby: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Dolby

* Creative: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Creative

* ICEPower: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/ICEPower

* Maxim: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Maxim

* Waves: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Waves

* Xperi: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Xperi


### Realtek Audio Control & HP Audio Control

https://github.com/alanfox2000/realtek-universal-audio-driver/releases


## Installation

### Universal Audio Driver

A. Using Universal Audio Driver Inf Editor

1. Lanuch Universal Audio Driver Inf Editor

2. Open Package, click "Open Package", select the parent folder which contains Realtek folders

Folder Struction

	`> UAD (Parent Folder)`

		`> Realtek (Universal Audio Driver)`

		`> Setup Program (Setup Program) *Optional (if you want Setup Program to install UAD)`

		`> ThirtyParty (Required if your OEM PC have preinstall Realtek UAD with installed audio enhacers e.g. Sound Blaster Cinema 5)`

2. Type Vender ID Device ID | SubVender ID | SubSystem ID, click "Check". If HardWare ID is not found, using Universal Audio Driver Inf Editor is not supported.

Harware ID = HDAUDIO\FUNC_01&VEN_10EC&DEV_1220&SUBSYS_1458355D

| Vender ID | Device ID | SubVender ID | SubSystem ID |
|-----------|-----------|--------------|--------------|
| 10EC      | 1220      | 1458         | 355D         |

3. Select "Setup program installation" or "INF installation", then click "Make Sausage"

4. Base on the two selections:

+ Setup program installation

	Right click Setup.exe, run as administrator

+ INF installation

	Right click InstallPackage.bat, run as administrator

5. Install Realtek Audio Control / HP Audio Control using UWP-Package-Installer (tutorial)



`pnputil /i /a <PATHTOINF>`
