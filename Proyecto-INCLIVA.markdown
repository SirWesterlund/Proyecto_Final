## --- Proyecto INCLIVA ---
![](Imágenes/image1.png)

## --- Índice ---
## 1. ¿Qué es INCLIVA?

    1.1 Introducción a la Unidad de Informática
        1.2 Servicios que ofrecen

## 2. Microsoft Teams

## 3. Backup

    3.1 ¿Qué es Proxmox?
        3.2 ¿Qué es Clonezilla?
            3.3 Creación y guardado de imagen
                3.4 Creación de máquina virtual y restauración de imagen

## 4. Virtual LAN

    4.1 ¿Qué nos proporciona las VLAN?
        4.2 Configuración de VLANs en switches
            4.3 Estructura final

## 5. Hardware

        5.1 Fuente de alimentación

## 6. Sistema de control de acceso en puertas

## 7. ¿Qué es pfSense?

        7.1 Ejemplo de instalación en VirtualBox
            7.2 Ejemplo de configuración OpenVPN Site-to-Site con SSL/TLS
                7.3 Estructura final

## 8. Bibliografía

        8.1 Sobre INCLIVA
            8.2 Guías de Clonezilla
                8.3 Guías de Proxmox
                    8.4 Configuración de switches
                        8.5 Guía de configuración OpenVPN Site-to-Site con SSL/TLS
## 9. Conclusiones 

## 1. ¿Qué es INCLIVA?

La Fundación para la Investigación del Hospital Clínico de la Comunidad
Valenciana INCLIVA gestiona la investigación biomédica del Hospital
Clínico Universitario de Valencia y su Departamento de Salud, así como
determinados grupos de excelencia científica de la Facultad de Medicina
de la Universidad de Valencia y de la Fundación Carlos Simón.

***1.1 Introducción a la Unidad de Informática***

Entre todos los servicios que ofrecen, nos vamos a centrar en la Unidad
de Informática que se encarga de mantener en funcionamiento todas las
infraestructuras informáticas, audiovisuales y de telecomunicaciones
ubicadas en las instalaciones de INCLIVA.

Asimismo proporciona soporte y asesoramiento técnico al personal de la
institución.

***1.2 Servicios que ofrecen***

Consultoría informática en proyectos, copias de seguridad, teletrabajo,
incidencias ordenadores, correo corporativo, telefonía, desarrollo web,
almacenamiento en nube, asesoramiento en compras.

Servicios de Supercomputación y Almacenamiento:

-   Acceso a recursos computacionales de alta capacidad.
-   Almacenamiento de datos.
-   Alojamiento, configuración y administración de infraestructura
    informática propia de los grupos de investigación en nuestro centro
    de procesamiento de datos.

A continuación, veremos herramientas utilizadas durante el período en
detalle con las que hemos trabajado:

## 2. Microsoft Teams

Microsoft Teams es una aplicación basada en la nube que es parte de
Microsoft Office 365 que sirve para realizar colaboraciones de trabajo
en equipo por, siendo ésta muy utilizada por las empresas, se pueden
crear chats, videollamadas e incluso organizar un calendario de
reuniones como se puede ver:

![](Imágenes/image3.png)

![](Imágenes/image4.png)

## 3. Backup

Los backups, son de las funciones más importantes que hay en el sector
de la informática ya que nos permite tener una copia exacta funcional de
un disco duro en otro equipo distinto por ejemplo. Una de las
actividades realizadas en INCLIVA fue restaurar una imagen de un
servidor Windows 11 a un servidor Proxmox con Clonezilla.

**Dato a destacar:** Clonezilla fue visto durante el primer año de Grado
Medio de SMR en el módulo de Sistemas Operativos, y Proxmox se iba a ver
en segundo de ASIR en el módulo de Administración de Sistemas
Operativos.

***3.1 ¿Qué es Proxmox?***

Proxmox o Proxmox Virtual Environment es un entorno de virtualización de
servidor de código abierto 100% libre y sin límites en su uso. Es una
distribución Linux basada en Debian que permite el despliegue y la
gestión de máquinas virtuales y contenedores. Incluye una consola web y
herramientas de línea de comandos.

![](Imágenes/image5.png)

Con Proxmox podemos crear máquinas virtuales usando el almacenamiento
físico del equipo que sea además de discos duros externos. El objetivo
era añadir un disco duro extraíble que en aquel caso era de 1TB y además
otro de 750GB ya que disponíamos de uno. En total este equipo tenía 3
discos, dos físicos y el extraíble.

***3.2 ¿Qué es Clonezilla?***

Es un software libre de recuperación de una imagen creada de un sistema
operativo, tiene diversas funcionalidades como crear una imagen del
sistema o eliminarla o por ejemplo eliminar una partición. Clonezilla
está diseñado por Steven Shiau y desarrollado por el NCHC Labs en
Taiwán. Clonezilla SE (Server Edition) ofrece soporte multicast (más de
40 ordenadores simultáneos) similares a Norton Ghost Corporate Edition.

![](Imágenes/image6.png)

Con la iso de Clonezilla instalada y puesta como primera opción de
arranque en el equipo de Windows 11, comenzamos primero con la
extracción de su imagen de disco.

***3.3 Creación y guardado de imagen***

Cuando carga Clonezilla nos pide elegir los modos de inicio, se escogió
la primera opción:

![](Imágenes/image7.png)

Después nos pedirá elegir idioma y distribución de teclado. Se puso en
español y la distribución de teclado se mantuvo por defecto que es la
inglesa.

![](Imágenes/image8.png)

![](Imágenes/image9.png)
![](Imágenes/image10.png)![](Imágenes/image11.png)

Tras eso nos pregunta donde guardaremos esa imagen, y en este caso como
son unidades locales seleccionamos la primera opción, le damos a "Enter"
para continuar y con eso posteriormente nos indica las unidades que ha
encontrado Clonezilla:

![](Imágenes/image12.png)

![](Imágenes/image13.png)

Ahora, nos aparecerán todas las particiones y nos toca seleccionar la
correcta que será en mi caso la del almacenamiento externo de 1TB. Con
esto se aclara que primero es elegir el disco al que se quiere guardar y
por último el de origen que sería el equipo que se quiere restaurar:

![](Imágenes/image14.png)

Aquí podemos hacer que Clonezilla revise si algo malo puede haber en el
disco, si sabemos que no, sencillamente le damos a la primera opción que
fue el caso:

![](Imágenes/image15.png)

Ahora nos pide elegir un directorio o archivo en donde almacenar esa
imagen en esa unidad. Puedes no tener nada y continuar pero más adelante
habrá que crear un repositorio de imágenes para
cuando lleguemos a la restauración

![](Imágenes/image16.png)

![](Imágenes/image17.png)![](Imágenes/image18.png)
\
Nos pide ahora elegir el modo de realización de tareas. Podemos
simplemente elegir "Beginner" y continuar:\
\
Tras lo anterior nos pregunta ahora qué queremos hacer, si guardar el
disco como imagen o sus particiones, en este caso se escogió la primera
opción:

![](Imágenes/image19.png)

Después nos pide el nombre que queremos que tenga la imagen:

![](Imágenes/image20.png)
\
Ahora nos pide la unidad de origen que sería la unidad del servidor de
Windows 11 cuyo tamaño es de 512GB:

![](Imágenes/image21.png)

Dejamos la opción -zip por defecto:

![](Imágenes/image22.png)

Como el disco está bien le damos a la primera opción que es -sfsck y
continuamos:

![](Imágenes/image23.png)

Le decimos que nos revise la imagen guardada para que al acabar de
guardarla nos diga Clonezilla si la imagen es restaurable:

![](Imágenes/image24.png)

Se podría encriptar la imagen pero en este caso no se realizó y
seleccionamos la primera opción:

![](Imágenes/image25.png)

Ahora nos pregunta qué hacer cuando termine todas las operaciones
seleccionadas. Siempre se usó -p choose.

![](Imágenes/image26.png)

Después nos aparece lo siguiente que es la descripción de la operación y
le damos a "y" para continuar:

![](Imágenes/image27.png)

Como Windows 11 tiene varias particiones saldrán varias pantallas como
la siguiente en donde se ve el progreso, el tiempo restante y más
información:

![](Imágenes/image28.png)

Cuando todo termina nos aparece este menú en donde podemos apagar el
equipo, reiniciar, entrar en el cmd y también comenzar de nuevo desde 3
puntos de guardado distinto. Siempre que no funcionaba algo lo
preferible era empezar de cero y darle a "rerun1".

![](Imágenes/image29.png)

***3.4 Creación de máquina virtual y restauración de imagen***

Con la imagen guardada ahora en el disco duro extraíble tenemos la
imagen del equipo a restaurar en el servidor Proxmox, entonces lo que
queda ahora es restaurar esa imagen desde el disco duro extraíble al
disco duro físico que añadirmos físicamente de 750GB.

Para conseguir esto, creamos una máquina virtual en el servidor Proxmox
desde remoto, ponemos nuestro PC en la red del equipo de Proxmox y
montamos un disco duro de la máquina virtual a un directorio en el que
contendrá el contenido de la imagen que hemos guardado.

A continuación debemos instalar una ISO de por ejemplo una Ubuntu 22.04
y la subimos a Proxmox para después añadírsela a la máquina virtual,
entonces hacemos lo siguiente en Proxomox:

Le damos a ISO Images, seleccionamos la ISO y le damos a "Upload"

![](Imágenes/image30.png)

Ahora es el turno de crear la máquina virtual, le damos a "Create VM",
le damos un nombre, añadimos la ISO donde pone ISO "image", en System lo
podemos dejar por defecto, en Disks seleccionamos en este caso del
almacenamiento principal, en CPU nos basta con 2 núcleos, de RAM 2GB
para mover Ubuntu, seleccionamos el adaptador de red y confirmamos:

![](Imágenes/image32.png)

![](Imágenes/image33.png)![](Imágenes/image34.png)

![](Imágenes/image35.png)

![](Imágenes/image36.png)

![](Imágenes/image38.png)

![](Imágenes/image39.png)

Ahora vamos a "Console" y arrancamos la máquina dándole a "Start":

![](Imágenes/image40.png)

Con la Ubuntu ya instalada, le pongo una dirección IP dentro de la red
de Proxmox y monto el directorio que en mi caso fue "/media/cart" en
formato ext4, con el siguiente comando... No hace falta que sea ntfs ya
que estamos haciendo esto en un entorno virtual:

**mount -t ext4 /dev/sdb1 */*media/cart****

**mount -t ext4 /dev/sdc1 */*media/sdc1****

Luego añadir lo necesario en el fichero fstab para que al reiniciar no
se pierda el punto de montaje:

Ahora con el disco duro de 750GB, creamos una partición con el comando
fdisk y creamos su punto de montaje y persistencia en fstab para después
añadir un disco de tipo "Disk Directory" al Proxmox que es en donde se
quedará la imagen:

**- Montaje y persistencia en la Ubuntu (para ver los puntos de montaje
usamos "mount"):**

![](Imágenes/image41.png)

![](Imágenes/image42.png)

**- Montaje y persistencia en el almacenamiento de destino del
Proxmox:**

![](Imágenes/image43.png)

Ahora queda que ese directorio contenga la imagen de disco entonces, lo
que se hizo fue un rsync desde otro PC hacia el disco duro extraíble y
copiar la imagen a la ruta "/media/cart":

![](Imágenes/image46.png)

Tras eso, creamos el repositorio de imágenes que contendrá la imagen:

![](Imágenes/image47.png)

Lo siguiente fue añadir 600 de los 750GB del otro disco, poner la iso
del Clonezilla al Proxmox, arrancarlo y seguir un poco lo mismo de los
pasos anteriores pero con algunas diferencias ya que ahora toca
restaurar. Tras hacer de nuevo lo de "local_dev" y añadir el disco donde
tenemos el repositorio de imágenes, seleccionamos ese directorio:

![](Imágenes/image48.png)

Nos pregunta de nuevo el modo de ejecución (Beginner o Expert),
seleccionamos "Beginner" y al darle nos salen varias opciones y
escogeremos "restoredisk":

![](Imágenes/image49.png)

Nos sale ahora la imagen a restaurar, la seleccionamos, seleccionamos el
disco de destino de 750GB, nos preguntará de nuevo el modo de ejecución
que seleccionaremos "Beginner" y con eso continuamos:

![](Imágenes/image51.png)

![](Imágenes/image52.png)

![](Imágenes/image53.png)

![](Imágenes/image54.png)

Ya con esto terminado tendríamos todo y debería funcionar. Tan sólo
queda comprobar si al poner la opción de arranque del Proxmox el disco
de 750GB se inicia Windows 11 y si al reiniciar no da ningún fallo.

![](Imágenes/image55.png)

## 4. Virtual LAN

En INCLIVA hacen uso de las Virtual LAN o también conocidas como "VLAN"
nos permite crear redes lógicamente independientes dentro de la misma
red física, haciendo uso de switches gestionables que soportan VLANs
para segmentar adecuadamente la red. También es muy importante que los
routers que utilicemos soportan VLAN, de lo contrario, no podremos
gestionarlas todas ni permitir o denegar la comunicación entre ellas.
Actualmente la mayoría de routers profesionales e incluso sistemas
operativos orientados a firewall/router como pfSense o OPNsense soportan
VLAN porque es un estándar hoy en día.

***4.1 ¿Qué nos proporciona las VLAN?***

1.  **Segmentación de la red:** Las VLAN permiten dividir la red en
    subredes virtuales, lo que facilita la organización de los equipos
    en grupos específicos como administradores, dispositivos IoT,
    invitados, etc. Esto ayuda a controlar el tráfico y mejorar la
    seguridad.

2.  **Flexibilidad:** con las VLAN, es fácil asignar equipos a
    diferentes subredes y aplicar políticas de comunicación, como
    permitir o bloquear el tráfico entre VLAN o a Internet. Por ejemplo,
    puede personalizar los servicios para los invitados.

3.  **Optimización de la red:** Al tener subredes más pequeñas, se
    reduce el dominio de transmisión y se mejora el rendimiento de la
    red evitando la congestión provocada por demasiado tráfico. Y además
    al utilizar VLAN, puede reducir la cantidad de enrutadores
    necesarios, lo que reduce la latencia y mejora el rendimiento
    general de la red.

**Dato a destacar:** Las VLAN han sido vistas en los módulos de Redes
Locales (1ºSMR) y Seguridad Informática (2ºSMR), además de primero de
ASIR en el módulo de Redes Locales.

***4.2 Configuración de VLANs en switches***

Llegaron dos switches Aruba a la empresa y tocó crear, configurar las
VLANs, configurar interfaces a cada switch además de poner algunas VLAN
en modo trunk, otras en modo access, el protocolo spanning tree con
prioridad en cada una, configurar la ip de acceso de cada switch y
también cambiar el nombre de host del switch. Empecemos con la
definición de los modos, el spanning tree:

-   **Modo access:** El modo de acceso se emplea en los entornos donde
    no están configuradas redes VLAN. El enrutador lleva el tráfico sin
    etiquetado VLAN y usa este modo para conectar dispositivos del
    usuario final tales como ordenadores portátiles, NAS e impresoras.

-   **Modo trunk:** El modo trunk se accede en un entorno configurado
    para VLAN y está diseñado para conectar dispositivos usando redes
    VLAN etiquetadas (p. ej., conmutadores y NIC habilitados para VLAN).
    Los puertos que utilizan el modo trunk se pueden enlazar entre
    varios dispositivos de red y pueden llevar tráfico entre varias
    redes VLAN.

-   **Protocolo Spanning Tree:** Es un protocolo de red de capa 2 del
    modelo OSI (capa de enlace de datos). Su función es la de gestionar
    la presencia de bucles en topologías de red debido a la existencia
    de enlaces redundantes (necesarios en muchos casos para garantizar
    la disponibilidad de las conexiones). El protocolo permite a los
    dispositivos de interconexión activar o desactivar automáticamente
    los enlaces de conexión, de forma que se garantice la eliminación de
    bucles. STP es transparente a las estaciones de usuario.

\- Para cambiar el nombre de host del switch sería escribir "config" y
después escribir:

**"hostname \<nombre-switch\>"**

\- Para crear una VLAN y darle un nombre escribimos "config" y desde ahí
hacemos:

**"vlan \<id-vlan\>"** y después **"name \<nombre-vlan\> \<id-vlan\>"**

\- Escribimos "config" y para meterse en un rango de interfaces y poner
una VLAN de un modo u otro hacemos:

**"int 1/1/5-1/1/19"**, con eso ya hemos accedido al rango y ahora
hacemos **"vlan access \<id-vlan\>"**

\- Para ponerla en modo trunk sería como antes con un ligero cambio:

**"int 1/1/5-1/1/19"**, con eso ya hemos accedido al rango y ahora
hacemos **"vlan trunk allowed \<id-vlan\>"**

-Para poner el protocolo spanning tree en cada vlan escribimos "config",
nos metemos en una interfaz y hacemos lo siguiente:

Escribimos el numero de la vlan que queramos **"vlan 90"** y al entrar
ponemos **"spanning-tree priority \<numero\>"**

-Para poner en una VLAN una IP de acceso al switch, escribimos "config"
y hacemos lo siguiente:

**"vlan \<numero\> ip address \<dirección-ip\>"**

![](Imágenes/image56.png)

***4.3 Estructura final***

![](Imágenes/image57.png)

## 5. Hardware

En INCLIVA resuelven incidencias relacionadas con hardware, ya sea en
ordenadores de sobremesa, periféricos u ordenadores portátiles. Una de
ellas fue el cambio de una fuente de alimentación de un sobremesa que le
había estallado uno de los capacitores.

***5.1 Fuente de alimentación***

Fue sencillo detectar el problema ya que a pesar de que la placa base
recibía corriente, al darle al botón de encendido no sucedía nada,
además el resto de componentes estaban en buen estado entonces tan sólo
quedaba ver qué le sucedía la fuente y resultó que era efectivamente el
problema. Aquel equipo tenía 3 unidades de almacenamiento, un SSD SATA
donde estaba el sistema operativo y dos discos duros. La antigua fuente
de alimentación tenía 3 conectores SATA pero la nueva fuente tiene sólo
2 aunque tiene una salida Molex, entonces la solución para conectar
todas las unidades era utilizar un adaptador de Molex macho con salida
de SATA:

![](Imágenes/image58.png)

![](Imágenes/image59.png)

**Dato a destacar:** Lo relacionado con hardware ha sido visto en el
módulo de Montaje y mantenimiento de equipos de primero de Grado Medio y
en Fundamentos Hardware en primero de ASIR.

## 6. Sistemas de control de acceso en puertas

INCLIVA cuenta con un sistema de control de acceso en puertas mediante
tarjetas identificativas que contienen la información sobre la identidad
del usuario. Las tarjetas son configuradas por software como Accesor,
que te permite confgurar qué puertas puede abrir una persona y cuales
no. Posteriormente estas tarjetas son impresas por una impresora de
tarjeta identificativa como la siguiente:\
\
![](Imágenes/image60.png)

**Dato a destacar:** Este tipo de sistema fue visto en el módulo de
Seguridad Informática de segundo de SMR y el segundo año de ASIR.

## 7. ¿Qué es pfSense?

Es un sistema operativo orientado a firewall a nivel profesional, tanto
en el ámbito doméstico con usuarios avanzados, como en pequeñas y
medianas empresas para segmentar su red correctamente y disponer de
cientos de servicios disponibles. pfSense está basado en el sistema
operativo FreeBSD, por tanto, tendremos la garantía de que es un sistema
operativo estable, robusto, y, sobre todo, muy seguro. A diferencia de
otros firewalls, pfSense dispone de una interfaz gráfica realmente
completa y muy intuitiva.

***7.1 Ejemplo de instalación en VirtualBox***

Nos vamos a la web para instalar la ISO de pfSense:

![](Imágenes/image61.png)
\
***

Nos vamos a VirtualBox y ponemos 2GB de RAM, 2 núcleos de procesador, el
almacenamiento se dejó en 16GB y añadimos la ISO al comienzo en "Imagen
ISO", también podemos añadirla más tarde. Cuando esté todo le damos a
terminar:

![](Imágenes/image62.png)

![](Imágenes/image64.png)

![](Imágenes/image65.png)

Ahora nos vamos a "Red", usamos "Adaptador Puente" y seleccionamos la
controladora de red que está recibiendo conexión:

![](Imágenes/image66.png)

Con todos estos pasos ya podemos arrancar la máquina. Una vez arrancada
nos saldrá qué hacer entre tres opciones. Al ser nueva le damos a la
primera:

![](Imágenes/image67.png)

Después de completar la instalación nos sale el siguiente menú con
opciones:

![](Imágenes/image68.png)

Aquí debemos elegir la opción 1 para asignar la interfaz de red, podemos
tener varias, en nuestro caso fue solo una. Una vez que está asignada
vamos a la opción 2 y ponemos nuestra dirección IP, Máscara de Red y
Gateway. Cuando finalizamos eso ya podemos acceder por navegador web a
la IP que le hemos asignado:

![](Imágenes/image69.png)

Las credenciales por defecto son "admin" de usuario y la contraseña es
"pfsense", después podemos cambiarlas. Antes de llegar a eso nos pide
usuario y contraseña y además un nombre de dominio para el firewall

Una vez dentro esto es lo que aparece:

![](Imágenes/image70.png)
\
Para cambiar las credenciales hacemos lo siguiente, nos vamos a System
\> User Manager \> Users y le damos al botón "Add":

![](Imágenes/image71.png)

Ponemos nuestro usuario y contraseña y además lo hacemos miembro del
grupo "admins", vamos abajo del todo y guardamos. Ahora podremos iniciar
sesión siempre con ese usuario:

![](Imágenes/image72.png)

***7.2 Ejemplo de configuración OpenVPN Site-to-Site con SSL/TLS***

Una conexión Site-to-Site con SSL/TLS sirve para conectar uno o más
sitios remotos y es especialmente conveniente para gestionar un gran
número de sitios remotos que se conectan de nuevo a un sitio central de
forma radial.

Al configurar una conexión OpenVPN Site-to-Site con SSL/TLS, un firewall
hará de servidor y los demás serán clientes.

OpenVPN es una herramienta que sirve para para conectarnos a Internet de
una manera segura desde cualquier red ya sea cableada o WiFi, con
cifrado WEP/WPA o sin cifrar. Todo el tráfico irá cifrado a través de un
túnel.

OpenVPN utiliza un conjunto de protocolos SSL/TLS que trabajan en la
capa de transporte. TUN es el que utlizaremos ya que con él se crea el
túnel.

Este estilo de VPN requiere una subred dedicada para la interconexión
OpenVPN entre redes además de las subredes en ambos extremos. La red del
túnel de OpenVPN será la 172.21.201.0/30. Cada cliente que se conecta
obtiene una subred /30 para interconectarse con el servidor.

Para llevar esto a cabo necesitamos en este caso, dos máquinas virtuales
que harán de pfSense y otras dos Ubuntu con nuestro servidor Proxmox y
los pasos a seguir a continuación:

Creamos las 4 máquinas:

![](Imágenes/image73.png)

Asignamos las IPs estáticas a las Ubuntu:

![](Imágenes/image74.png)

Antes de meternos a configurar los pfSense, añadiremos el "tag"
correspondiente a cada máquina en la tarjeta de red:

Ubuntu-Cephei tiene el 102:

![](Imágenes/image75.png)

Ubuntu-Cygni tiene el 103:

![](Imágenes/image76.png)

Para las pfSense usaremos la misma tarjeta de red pero le haremos una
pata extra para que comuniquen con las máquinas Ubuntu respectivamente.
Para el pfSense-Cephei tendremos el 101 y 102:

![](Imágenes/image77.png)

Y la pfSense-Cygni tiene el 101 y 103:

![](Imágenes/image78.png)

Algo muy importante que hizo falta fue un USB, ya que desde esa red no
se podía salir a internet ni había SSH, entonces lo que se hizo fue
poner un USB físico al servidor Proxmox para así poder transferir los
ficheros necesarios a la máquina del cliente ya que si tenemos un USB
físico podemos ir moviéndolo de una máquina a otra como si estuviéramos
conectándolo de un ordenador a otro.

![](Imágenes/image79.png)

Ahora nos toca configurar los pfSense y el resultado es este:

pfSense-Cephei:

![](Imágenes/image80.png)

pfSense-Cygni:

![](Imágenes/image81.png)


Ahora desde las máquinas Ubuntu ponemos la IP de la LAN correspondiente
a su pfSense:

![](Imágenes/image82.png)

Configuramos lo de las credenciales y nos ponemos manos a la obra con
los certificados. Primero comencemos con la autoridad de certificación:

![](Imágenes/image83.png)

Ahora el certificado del servidor:

![](Imágenes/image84.png)

Es el turno del certificado del cliente:

![](Imágenes/image86.png)

Tenemos todos los certificados, ahora tenemos que usarlos en
Ubuntu-Cygni. Con nuestro USB conectado en Ubuntu-Cephei nos copiamos
todo tras descargarlos dándole al asterisco, también nos descargamos la
clave privada del cliente dándole al icono de la llave:

![](Imágenes/image87.png)

![](Imágenes/image88.png)

Ahora desde Ubuntu-Cephei añadimos los datos del cliente:

![](Imágenes/image90.png)

![](Imágenes/image91.png)

Tenemos que añadir un par de reglas de firewall en ambas Ubuntu para
comprobar que puedan hacerse ping desde la terminal (aunque desde la
interfaz pfSense se puede probar) y sobretodo que puedan contactar sin
problema. Las reglas son las siguientes:

![](Imágenes/image92.png)

Ahora añadimos una regla para la OpenVPN para pasar tráfico a través de
la VPN desde la LAN del lado del Cliente a la LAN del lado del Servido
por el túnel. Puede ser una regla del estilo \"Permitir todo\" o un
conjunto de reglas más estrictas. Este ejemplo permite todo el tráfico:

![](Imágenes/image93.png)

Ahora en el cliente (Ubuntu-Cygni), importamos el certificado de CA
junto con el certificado de cliente, la clave privada del cliente, la
clave TLS del servidor y creamos el cliente OpenVPN:

![](Imágenes/image94.png)

![](Imágenes/image95.png)

Aquí está la clave TLS del servidor que
tenemos que copiar y pegar:

![](Imágenes/image96.png)

![](Imágenes/image97.png)

Con esto último configurado podemos realizar una serie de
comprobaciones:

![](Imágenes/image98.png)

![](Imágenes/image99.png)\
\
Aquí vemos que el cliente llega al servidor:

![](Imágenes/image100.png)

Lo único que nos queda es hacer que ambas máquinas pudieran contactarse
e incluso que pudieran acceder al pfSense que no era el suyo. Para eso
añadimos una nueva regla de firewall en el cliente que será la misma que
pusimos en el servidor:

![](Imágenes/image101.png)

Y comprobamos si ambas máquinas pueden accederse entre ellas:

![](Imágenes/image102.png)

![](Imágenes/image103.png)

![](Imágenes/image104.png)**\
\
Dato a destacar:** OpenVPN se vió en segundo de ASIR en el módulo de
Seguridad Informática y la configuración de reglas de firewall se vieron
también en segundo de ASIR en el módulo de Seguridad Informática.

## 7.3 Estructura final

![](Imágenes/image105.png)

## 8. Bibliografía

Aquí están los enlaces que han sido útiles para llevar todo a cabo:

***8.1 Sobre INCLIVA***

<https://www.incliva.es/>

***8.2 Guías de Clonezilla***

<https://www.youtube.com/watch?v=nBP_XhhcTAY>

<https://www.carm.es/edu/pub/04_2015/6_3_1_contenido.html>

***8.3 Guías de Proxmox***

[*https://tutoriales.cect.org/anadir-a-proxmox-un-disco-duro-para-almacenamiento/*](https://tutoriales.cect.org/anadir-a-proxmox-un-disco-duro-para-almacenamiento/)

***8.4 C*onfiguración de switches**

[https://www.arubanetworks.com/techdocs/centralonprem/254/content/nms-on-prem/getting_started/cli.htm](https://www.arubanetworks.com/techdocs/centralonprem/254/content/nms-on-prem/getting_started/cli.html)l

<https://www.arubanetworks.com/techdocs/ArubaOS_62_Web_Help/Content/ArubaFrameStyles/Network_Parameters/Configuring_VLANs.html>

<https://www.arubanetworks.com/techdocs/CLI-Bank/Content/cppm/con-hst.html>

<https://www.arubanetworks.com/techdocs/AOS-CX/10.07/HTML/5200-7866/Content/Chp_stp/mstp_cmds/spa-tre-pri.html>

***8.5 Guía de configuración OpenVPN Site-to-Site con SSL/TLS***

<https://docs.netgate.com/pfsense/en/latest/recipes/openvpn-s2s-tls.html>


## 9. Conclusiones

Se han realizado tareas bastante comunes dentro del sector de la informática, ha sido entretenido y se ha aprendido cosas nuevas, todo un placer.


                            David Tronchoni González 2ºASIR 
                            IES La Sénia Curso 2023-2024