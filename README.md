# PaPer_DJ-Hacks-PS2
PaPer_DJ-Hacks-PS2 (Free McBoot)

----------------------------------------------------------------------------------
INFO FREE MCBOOT & TOOLS:

* https://www.mur3.com/ps2-instalar-free-mcboot-1-95-de-una-memory-card-a-otra/

* https://www.youtube.com/playlist?list=PLJ4Qqog0UI_UWALVtoQZL1oWgml2b88S7

* https://github.com/ifcaro/Open-PS2-Loader

* http://www.ps2-home.com/forum/viewforum.php?f=13


PS2 | INSTALAR FREE MCBOOT 1.95 DE UNA MEMORY CARD A OTRA
* https://youtu.be/OBdYhtOzkn4

PS2 | INSTALAR OPL 0.9.3 Y CONFIGURACION INICIAL
* https://youtu.be/50PN_lChyrY

ULTIMA Y MEJOR VERSION ESTABLE DE OPL
* OPL 0.9.4 Rev.1564 ALL.zip

MANAGER (Software) para gestionar los juegos y caratulas PS2 en el PC
* https://oplmanager.com/site/

UTILIZAR MANDOS USB O BLUETOOTH (PS3, PS4) EN LA PS2 (PADEMU)
* http://www.ps2-home.com/forum/viewtopic.php?f=30&t=7447&sid=05ef402a0a321bbecc5f5b714b35fd58
  * Quick tutorial: 
1) Install latest OPL Daily Build and launch it.
2) Press Triangle on the game and go to PADEMU 
3) Enable emulator for 1P and 2P and vibration (if desired) 
4) Plug in each controller via usb cable and click on pair. 
5) Save settings and then test in your favorite game!

(Bluetooth usb adapters needs to support EDR)



DOWNLOADS:

* https://www.mur3.com/playstation-2/
TEU 4.0 PS2 (Todo en UNO Iso para PS2) 
(Incluido en lista de archivos)

* http://psx-scene.com/forums/official-open-ps2-loader-forum/

* http://www.ps2-home.com/forum/viewforum.php?f=64

EMULATION:

* https://pcsx2.net/

----------------------------------------------------------------------------------

MONTAR SERVIDOR SAMBA (SMB) PARA CARGAR ISOS MEDIANTE RED LOCAL (LAN)

* https://foro.seguridadwireless.net/openwrt/(tutorial)configura-samba-para-cargar-por-red-tus-juegos-de-ps2/

* https://www.elotrolado.net/hilo_tutorial-servidor-smb-en-raspberry-pi-para-playstation-2_2188596

PS2 OPL SMB with Android Box for playing PS2 games over LAN/WIFI
* https://www.youtube.com/watch?v=lmUlW3PNsI8

Jugar Isos PS2 por cable de Red bien explicado
* https://www.youtube.com/watch?v=iHfULbnYUe0

Diferencias en cargar juegos de PS2 entre USB y SMB
* https://www.youtube.com/watch?v=bbOuO7B9d3E

CARGAR JUEGOS DE PS1 por cable de Red
* http://www.ps2-home.com/forum/viewtopic.php?t=7236
* https://www.youtube.com/watch?v=R4WUInFqsbc

CONVERTIR JUEGOS DE .BIN .CUE A .ISO
 > keep in mind that OPL Manager has a built in BIN to ISO converter. -- it doesn't get any easier than that! :) 
Go to Tools / select Disc/Convert to ISO.

[APP] PS2 BIN2ISO v0.1
* http://www.ps2-home.com/forum/viewtopic.php?f=27&t=548

* http://www.ps2-home.com/forum/viewtopic.php?t=2290

[APP] EzISO Renamer - Rename your ISO files with one click

Place this file next to your "DVD" and "CD" folders (the ones you created for OPL), launch the program and sit back.
In a few seconds your ISO library will be correctly renamed.

The program will automatically detect:
- Files that are already named correctly (will be skipped)
- File extensions that are in uppercase (files will be renamed to *.iso instead of *.ISO)
- Filenames that are longer than 32 characters (will be skipped)

From version 1.2, you can also drag and drop iso files or directories containing iso file on the program's icon to process them instantly.
* http://psx-scene.com/forums/f150/eziso-renamer-rename-your-iso-files-one-click-117233/

----------------------------------------------------------------------------------

  > Configuración de PS2 en OPL para SAMBA:

Abrimos el bloc de notas/Notepad++ y escribimos la configuración de red que tendrá la PS2:
Código: [Seleccionar]
IP MASCARA IPROUTER
y lo guardamos como IPCONFIG.DAT (es importante las mayusculas).
Un ejemplo, yo en mi red uso el rango de ips 192.168.2.0/24 . Si no estas seguro que ip darle a la ps2 coloca una bien alta como .240 
Citar
192.168.2.10 255.255.255.0 192.168.2.1

Una vez guardado el archivo IPCONFIG.DAT lo guardamos en un pendrive con formato FAT32.
Encendemos la PS2 y entramos a uLaunchELF
Y copiamos el archivo IPCONFIG.DAT de mass:/ a mc0:/SYS-CONF/


Una vez copiado el archivo, ya podemos salir y extraer el pendrive.

Ahora encendemos la PS2 y entramos en el OpenLoader
Entramos en Network config y veremos que la parte que pone - PS2 - ya esta configurada.

En la parte de -PC- ponemos:
IP: la del router (192.168.2.1)
Port: dejamos el que esta (445)
Share: borramos todo lo que haya (se configura solo)
User: nuestro usuario de SMB (ps2)
Password: la contraseña del usuario
Con todo esto le damos a OK

Estando en el menú vamos a Settings
Bajamos hasta ETH device start mode y lo ponemos en AUTO
Y en Default menu en ETH Games
Ya le podemos dar a OK


En el menú de nuevo guardamos los cambios con "Save changes" y salimos y volvemos entrar.
Cuando vuelva a entrar veremos que el programa va solo a la pestaña "ETH Games" y que vemos la carpeta PS2SMB si entramos en ella veremos los juegos.


4.- Anexo:
Formato de juegos:
Solo se aceptan formatos .iso y la imagen no puede haber sido modificada, es decir no van a funcionar juegos que eran CD y han sido parcheados para grabarlos en un DVD. Tampoco funcionaran mods en juegos como el san andreas PTMG. (en la versión 0.9.2) 
SOLO en la versión nigtly (Rev 789 Commit d871920) las .iso modificadas funcionan.
Solo se leerán las .iso que tengan como nombre el siguiente patrón:
      código_juego.nombre.iso
      
BIEN: SCUS_973.28.GT4.iso
MAL:    SCUS-973.28.GT4.ISO

El nombre (GT4) es lo que se verá en la lista de juegos y no puede superar los 32 carácteres.
¿Cómo obtengo el código del juego?
Existen listas por internet, ver en la epigrafía del disco, en el lateral de la caratula. Pero el método que siempre me ha funcionado es abrir la .iso con winrar,Ultraiso o descomprimirla y en la raiz de la .iso veremos un archivo llamado SLES_XXXX o SCUS_XXXX ese es el código.

----------------------------------------------------------------------------------

  * Open PS2 Loader

Copyright 2013, Ifcaro & jimmikaelkael
Licenced under Academic Free License version 3.0
Review LICENSE file for further details.

Introduction
Open PS2 Loader (OPL) is a 100% Open source game and application loader for the PS2 and PS3 units. It supports three categories of devices : USB mass storage devices, SMB shares and the PlayStation 2 HDD unit. USB devices and SMB shares support USBExtreme and *.ISO formats while PS2 HDD supports HDLoader format. It's now the most compatible homebrew loader.

OPL is also developed continuously - anyone can contribute improvements to the project due to its open source nature.

You can visit the Open PS2 Loader forum at:

http://psx-scene.com/forums/official-open-ps2-loader-forum/

For updated compatibility list, you can visit OPL-CL site at:

http://sx.sytes.net/oplcl/games.aspx

Release types
Open PS2 Loader bundle included several types of the same OPL version. These types come with more or less features included.

Type (can be a combination)	Description
"Normal" (No suffixes)	Regular, basic OPL release, without any extra features. Aka vanilla build.
"Childproof"	OPL release with some controls disabled (e.g. write operations).
"VMC"	OPL release with Virtual Memory Card (VMC) support.
"GSM"	OPL release with GSM integrated into it.
"PS2RD"	OPL release with PS2RD Cheat Engine built-in feature.
How to use
OPL uses the following directory tree structure across HDD, SMB, and USB modes:

Folder	Description	Modes
"CD"	for games on CD media - i.e. blue-bottom discs	USB and SMB
"DVD"	for DVD5 and DVD9 images if using the NTFS file system on USB or SMB ; DVD9 images must be split and placed into the device root if using the FAT32 file system on USB or SMB	USB and SMB
"VMC"	for Virtual Memory Card images - from 8MB up to 64MB	all
"CFG"	for saving per-game configuration files	all
"ART"	for game art images	all
"THM"	for themes support	all
"CHT"	for cheats files	all
"CFG-DEV"	for saving per-game configuration files, when used from a OPL dev build - aka beta build	all
OPL will automatically create the above directory structure the first time you launch it and enable your favourite device. For HDD users, a 128Mb +OPL partition will be created (you can enlarge it using uLaunchELF if you need to).

USB
Game files on USB must be perfectly defragmented either file by file or by whole drive, and Dual Layer DVD9 images must be split to avoid the 4GB limitations of the FAT32 file system. We recommend Auslogics Disk Defrag for best defragging results.

http://www.auslogics.com/en/software/disk-defrag/

You also need a PC program to convert or split games into USB Advance/Extreme format, such as USBUtil 2.0.

SMB
For loading games by SMB protocol you need to share a folder (ex: PS2SMB) on the host machine or NAS device and make sure that it has full read and write permissions. USB Advance/Extreme format is optional - *.ISO images are supported using the folder structure above with the added bonus that DVD9 images don't have to be split if your SMB device uses the NTFS or EXT3/4 file system.

HDD
For PS2, 48-bit LBA internal HDDs up to 2TB are supported. They have to be formatted with either HDLoader or uLaunchELF (uLaunchELF is recommended).

To launch OPL, you can use any of the existing methods for loading an executable elf.

On PS3, you need an original SwapMagic 3.6+ or 3.8 disc (at the moment there aren't any other options). The steps for loading OPL on a PS3 are:

Rename OPNPS2LD.ELF to SMBOOT0.ELF
Make a folder in root of USB device called SWAPMAGIC and copy SMBOOT0.ELF to it.
Launch SwapMagic in PS3 and press UP+L1 then Open PS2 Loader should start.
There are 4 forms for launching elfs in SwapMagic.

SMBOOT0.ELF = UP + L1
SMBOOT1.ELF = UP + L2
SMBOOT2.ELF = UP + R1
SMBOOT3.ELF = UP + R2

Note: on PS3, only USB and SMB modes are supported.

Some notes for devs
Open PS2 Loader needs the latest PS2SDK:

https://github.com/ps2dev/ps2sdk
