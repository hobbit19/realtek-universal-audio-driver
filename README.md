# Realtek Universal Audio Driver (UAD)

#### Repository Updated: 30/7/2018

---------------------------------------

## Table of Contents
- [Lastest Infomation](#lastest-info)
- [Requirement](#requirement)
- [Download](#download)
- [Installation](#installation)
- [Uninstallation](#uninstallation)

---------------------------------------

<h2 id="lastest-info">Lastest Infomation</h2>

My Digital Life:

https://forums.mydigitallife.net/threads/update-realtek-high-definition-audio.72236/

Station-Drivers:

https://www.station-drivers.com/index.php?option=com_kunena&view=topic&catid=18&id=17&Itemid=858&lang=en

---------------------------------------

<h2 id="requirement">Requirement</h2>

Operating System: At least Windows 10 Version 1709 (64 Bit)


Unintall Realtek HDA Driver first!!!

Realtek HD Audio Codec Driver Patcher (A1) by Pihto (DTSi &DLL unlock) not work on UAD

---------------------------------------

<h2 id="download">Download</h2>

### Universal Audio Driver

https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/Realtek

### Setup Program for UAD

https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/XSetup

### Universal Audio Driver Inf Editor

1.3.0: https://drop.me/B4bZmE

### Third Party

* All Third Party: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty

* A-Volute: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/A-Volute

* Dolby: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Dolby

* Creative: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Creative

* ICEPower: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/ICEPower

* Maxim: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Maxim

* Waves: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Waves

* Xperi: https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/alanfox2000/realtek-universal-audio-driver/tree/master/UAD/ThirdParty/Xperi

### Control Panel

Download form Github: https://github.com/alanfox2000/realtek-universal-audio-driver/releases

Realtek Audio Control

URL: https://www.microsoft.com/en-us/store/p/realtek-audio-control/9p2b8mcsvpln

URI ms-windows-store://pdp/?PFN=RealtekSemiconductorCorp.RealtekAudioControl_dt26b99r8h8gj

HP Audio Control

URL: https://www.microsoft.com/en-us/p/hp-audio-control/9n77pw08dt9s

URI: ms-windows-store://pdp/?PFN=RealtekSemiconductorCorp.HPAudioControl_dt26b99r8h8gj

---------------------------------------

<h2 id="installation">Installation</h2>

### Universal Audio Driver

#### A. Using Universal Audio Driver Inf Editor

1. Lanuch Universal Audio Driver Inf Editor

2. Open Package, click "Open Package", select the parent folder which contains Realtek folders

	Folder Structure

	+ UAD (Parent Folder)

		+ Realtek (Universal Audio Driver)

		+ Setup Program (if you want Setup Program to install UAD)

		+ ThirtyParty (Required if your OEM PC have preinstall Realtek UAD with installed audio enhancer(s))

3. Type Vender ID, Device ID, SubVender ID and SubSystem ID, click "Check". If HardWare ID is not found, using Universal Audio Driver Inf Editor is not supported.

	Harware ID = HDAUDIO\FUNC_01&VEN_10EC&DEV_1220&SUBSYS_1458355D

	| Vender ID | Device ID | SubVender ID | SubSystem ID |
	|-----------|-----------|--------------|--------------|
	| 10EC      | 1220      | 1458         | 355D         |

4. Select "Setup program installation" or "INF installation", then click "Make Sausage"

5. Base on the two selections:

+ Setup program installation

   Right click Setup.exe, run as administrator

+ INF installation

   Right click InstallPackage.bat, run as administrator

5. Install Realtek Audio Control / HP Audio Control using <a href="https://github.com/colinkiama/UWP-Package-Installer">UWP-Package-Installer</a> (<a href="http://puresoftapps.blogspot.com/2018/07/uwp-package-installer-easiest-way-to.html">Tutorial</a>)

#### B. Using PnPUtil (Only for user who have "Hardware ID is not found" error when using Universal Audio Driver Inf Editor)

1. Find the Device ID that match HDXRT.inf or HDXRTSST.inf in Codec_xxxx folder

	Hardware ID = HDAUDIO\FUNC_01&VEN_10EC&DEV_0887&SUBSYS_10438577

	| Vender ID | Device ID | SubVender ID | SubSystem ID |
	|-----------|-----------|--------------|--------------|
	| 10EC      | 0887      | 1043         | 8577         |
	

2. Install the UAD driver (Codec_XXXX folder)
 
	 HDXRT.inf
	 
	`PnPUtil /i /a D:\UAD\Realtek\Codec_8501\HDXRT.inf`
 
	 HDXRTSST.inf
	 
	`PnPUtil /i /a D:\UAD\Realtek\Codec_8501\HDXRTSST.inf`

3. Install the Realtek Device Extension (CodecExtOem_RTK_XXXX folder)

	 HDXRTSST.inf
	 
	`PnPUtil /i /a D:\UAD\Realtek\CodecExtOem_RTK_8492\HDX_GenericExt_RTK.inf`

---------------------------------------

<h2 id="uninstallation">Uninstallation</h2>

### A. Uninstall through Control Panel (for setup program installation only)

1. Open Control Panel. Find "Realtek High Definition Audio Driver" , right click and select "Uninstall"

### B. Uninstall through Device Manager and DriverStoreExplorer

1. Stop "RtkAudioUniversalService" services on Task Manager

2. Uninstall and delete all Realtek software component first

![GITHUB](https://2.bp.blogspot.com/-T5210I3DARo/Wx_V59vt6HI/AAAAAAAAB_Y/0hb505aUk6QuHFO8y5-DGNiRp3WcPuBIgCLcBGAs/s1600/2.png)

3. Uninstall and delete Realtek Audio Device 

![GITHUB](https://1.bp.blogspot.com/-qRLK7Unoa3A/Wx_V5zVwy2I/AAAAAAAAB_U/0l-X3HKG2EEUZmBu8-k6UeomyD6PKs1ugCLcBGAs/s1600/1png.png)

4. Open DriverStoreExplorer, delete Realtek Device Extension

![GITHUB](https://2.bp.blogspot.com/-zHukGT061Pk/Wx_V6U7rmaI/AAAAAAAAB_g/2-AFCVXjaG4_-9ZfIwCBRQcAHhclRCWjQCLcBGAs/s1600/4.png)

5. Run cmd as administrator, type `sc delete RtkAudioUniversalService`

6. Rescan device

![GITHUB](https://3.bp.blogspot.com/-u_FM2PXq7-0/Wx_V6IWAN5I/AAAAAAAAB_c/RSUXoaavcMkTjQx_EGh_-fL1fKZIvD7tQCLcBGAs/s1600/3.png)

