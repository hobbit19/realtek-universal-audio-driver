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

---------------------------------------

## Installation

### Universal Audio Driver

A. Using Universal Audio Driver Inf Editor

1. Lanuch Universal Audio Driver Inf Editor

2. Open Package, click "Open Package", select the parent folder which contains Realtek folders

	Folder Structure

	+ UAD (Parent Folder)

		+ Realtek (Universal Audio Driver)

		+ Setup Program (if you want Setup Program to install UAD)

		+ ThirtyParty (Required if your OEM PC have preinstall Realtek UAD with installed audio enhancer(s))

3. Type Vender ID Device ID | SubVender ID | SubSystem ID, click "Check". If HardWare ID is not found, using Universal Audio Driver Inf Editor is not supported.

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

B. Using PnPUtil (Only for user who have "Hardware ID is not found" error when using Universal Audio Driver Inf Editor)

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
