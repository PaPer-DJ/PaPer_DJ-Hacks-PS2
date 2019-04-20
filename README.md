# PaPer_DJ-Hacks-PS2
PaPer_DJ-Hacks-PS2 (Free McBoot)

----------------------------------------------------------------------------------
INFO FREE MCBOOT & TOOLS:

* https://www.mur3.com/ps2-instalar-free-mcboot-1-95-de-una-memory-card-a-otra/

* https://www.youtube.com/playlist?list=PLJ4Qqog0UI_UWALVtoQZL1oWgml2b88S7

PS2 | INSTALAR FREE MCBOOT 1.95 DE UNA MEMORY CARD A OTRA
* https://youtu.be/OBdYhtOzkn4

PS2 | INSTALAR OPL 0.9.3 Y CONFIGURACION INICIAL
* https://youtu.be/50PN_lChyrY

DOWNLOADS:

* https://www.mur3.com/playstation-2/

TEU 4.0 PS2 (Todo en UNO Iso para PS2) 
(Incluido en lista de archivos)

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


  > Configuración de PS2:

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



