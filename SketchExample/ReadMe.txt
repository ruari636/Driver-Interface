; Copyright (c) Future Technology Devices International 2015



; THIS SOFTWARE IS PROVIDED BY FUTURE TECHNOLOGY DEVICES INTERNATIONAL LIMITED ``AS IS'' AND ANY EXPRESS
; OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS
; FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL FUTURE TECHNOLOGY DEVICES INTERNATIONAL LIMITED
; BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
; BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
; INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
; (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF
; THE POSSIBILITY OF SUCH DAMAGE.


Objective: 
==========
This ReadMe file contains the details of Sketch application release package. 



This application demonstrates interactive sketching using sketch, slider & button commands based on FT800 platform.


Release package contents:
=========================
The folder structure is shown as below.


+---Bin
|   \---Msvc_win32
|          \--libMPSSE.a - MPSSE library file.
|          \--ftd2xx.lib - FTD2XX library.
|          \--LibFT4222.lib - FT4222 library file.
|   \---MSVC_Emulator
|          \--ft8xxemu.lib - Emulator library file.               
+---Hdr
|
|   \---FT90X
|		\---\FT_DataTypes.h
|  		\---\FT_Platform.h
|
|   \---Msvc_win32
|   		\---\ftd2xx.h - ftd2xx header file
|   		\---\libMPSSE_spi - MPSSE header file
|		\---\FT_DataTypes.h - Includes the FT800 	
|					datatypes according to the platform.
|   		\---\FT_Platform.h - Includes Platform specific 
|							macros.
|                \---\LibFT4222.h - LibFT4222 header file 
|   \---MSVC_Emulator
|		\---\FT_Emulator.h
|		\---\FT_DataTypes.h - Includes the FT800 	
|					datatypes according to the platform.
|		\---\FT_EmulatorMain.h
|		\---\FT_Emulatorspi_i2c.h		
|   		\---\FT_Platform.h - Includes Platform specific 
|							macros.
|   \---\FT_CoPro_Cmds.h  - Includes the Coprocessor 	
|							commands.
|   \---\FT_Gpu.h - Includes the GPU commands.
|   \---\FT_Gpu_Hal.h - Includes the GPU HAL commands.
|   \---\FT_Hal_Utils.h - Includes the HAL utilities.
|
+---Project
|   \---Arduino
|   	\---FT_App_Sketch - project folder of Sketch Demo application based on arduino IDE  
| 		\---\FT_App_Sketch.ino - Sketch file of Sketch Demo application
| 		\---\FT_CoPro_Cmds.cpp - Coprocessor commands source file.
|   		\---\FT_CoPro_Cmds.h  - Includes the Coprocessor commands.
|  		\---\FT_DataTypes.h - Includes the FT800 datatypes.
|   		\---\FT_Gpu.h - Includes the Gpu commands.
|   		\---\FT_Gpu_Hal.cpp - GPU HAL source.
|   		\---\FT_Gpu_Hal.h - Includes the GPU HAL commands.
|   		\---\FT_Hal_Utils.h - Includes the HAL utilities.
|   		\---\FT_Platform.h - Includes Platform specific commands.
|
|   \---FT90x
|        \---FT_App_Sketch
|		\---.cproject
|		\---.project
|
|   \---MSVC_Emulator
|       \---FT_App_Sketch
|		\---FT_App_Sketch.sln solution file of Sketch Demo Emulator application
|		\---FT_App_Sketch.vcxproj  project file of Sketch Demo Emulator application
|		\---FT_App_Sketch.vcxproj.filters
|
|   \---Msvc_win32
|       \---FT_App_Sketch - project folder of Sketch Demo application based on MSVC/PC platform
|		\---Ft_App_Sketch.sln  solution file of Sketch Demo application
|		\---Ft_App_Sketch.vcxproj  project file of Sketch Demo application
|		\---Ft_App_Sketch.vcxproj.filters
|
+---Src
|   	\---FT_CoPro_Cmds.c - Coprocessor commands source file.
|   	\---FT_Gpu_Hal.c - Gpu hal source commands file.
|   	\---FT_App_Sketch.c - Main file of Sketch.
|   	\---FT_Emu_main.cpp	- Main file of Emulator
|
+--Test  folder containing input test files such as .wav, .jpg, .raw etc


Configuration Instructions:
===========================
This section contains details regarding various configurations supported by this software.

The configurations can be enabled/disabled via commenting/uncommenting macors in FT_Platform.h file. 
For MVSC/PC platform please look into .\FT_App_Sketch\Hdr\Msvc_win32\FT_Platform.h 
For arduino platform please look into .\FT_App_Sketch\Project\Arduino\FT_App_Sketch\FT_Platform.h
For FT90x platform please look into .\FT_App_Sketch\Hdr\FT90x\FT_Platform.h
For MVSC/PC Emulator platform please look into .\FT_App_Sketch\Hdr\MSVC_Emulator\FT_Platform.h 





Installation Instruction:
=========================

Unzip the package onto a respective project folder and open the solution/sketch file in the project folder and execute it. 
For MSVC/PC platform please execute .\FT_App_Sketch\Project\Msvc_win32\FT_App_Sketch\FT_App_Sketch.sln solution. 
For Arduino platform please execute.\FT_App_Sketch\Project\Arduino\FT_App_Sketch\FT_App_Sketch.ino sketch.
For MVSC/PC Emulator platform please execute .\FT_App_Sketch\Project\MSVC_Emulator\FT_App_Sketch\FT_App_Sketch.sln solution. 
For FT90x platform please import the project files in the .\FT_App_Sketch\Project\FT90x\FT_App_Sketch\ directory to the FTDI eclipse IDE.

The MSVC project file is compatible with Microsoft visual C++ version 2010.
The arduino project file is compatible with Arduino 1.0.5.
The MSVC emulator project is compatible with Microsoft Visual C++ version 2012 or above.
Reference Information:
======================
Please refer to AN_FT_App_Sketch for more information on application design, setup etc.
Please refer to FT800_Programmer_Guide for more information on programming FT800.
Please refer to the FT90x installation apps notes in the FTDI website.

Known issues:
=============
1. This application contains only SPI interface to FT800.
2. The SPI host(Arduino, Windows PC) are assuming the data layout in memory as Little Endian format. 


Extra Information:
==================
N.A


Release Notes (Version Significance):
=====================================
Version 4.3 - Updated to version 3.2 of HAL library
Version 4.2 - Addition of the latest emulator library
Version 4.1 - Added support for VM810C50 module for msvc platform.
Version 4.0 - Added support for FT81x series and FT90x series.
version 3.1 - Jun/13/2014 - Application now uses CMD_CSKETCH for FT801 platform.
Version 3.0 - Support for FT801 platform.
Version 2.0 - Support for FT800 emulator platform.
Version 1.0 - Final version based on the requirements.
Version 0.1 - intial draft of the release notes



