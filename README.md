# Parte 1

### Sistema operativo:

- Software principal de una maquina.
- Permite interactuar con el Hardware.

---

### Hipervisor:

- Software, firmware o Hardware que permite crear maquinas virtuales.

### Tipo 1:

- No requeire un software externo.
- Se instala directamente al hardware.
- Kernel based.
- Sirve para produccion.

### Tipo 2:

- Requiere un sistema operativo.
- Ambito de pruebas

---

### FAT12 :

- File system contains 1.5 bytes per cluster within the file allocation table.
- File system of floppy disk.
- It does not support layered structure, cluster addressed is only 12 bytes, which make the controlling of FAT a little difficult, and it only supports at most 32M partition.

---

### FAT16:

- File Allocation Table 16 bits
- The configuration files of every sector are expressed by 16 bytes in FAT16 and this is why it is named FAT16

---

### FAT32:

- File Allocation Table 32 bits
- Maximum file size is only around 4 gigabytes.
- Maximum size of a FAT32 partition is around 2 terabytes.

---

### VFAT:

- Virtual File Allocation Table
- Extension of the FAT file system and was introduced with Windows 95

---

### exFat:

- Introduced by Microsoft in 2006
- Optimized for flash memory such as USB flash drives and SD cards.
- exFAT can be used where NTFS is not a feasible solution.

---

### NTFS:

- New Technology File System.
- File-level encryption called the Encrypting File System (EFS)

---

### EXT3:

- Third extended filesystem
- Journaled file system that is commonly used by the Linux kernel. (Journaled file system: keeps track of changes not yet committed to the file system's main part by recording the intentions of such changes in a data structure known as a "journal")

---

### EXT4:

- Backward-compatible with ext3.
- Large file system:
    - support volumes with sizes up to 1 exbibyte (EiB) and single files with sizes up to 16 tebibytes (TiB)
- Persistent pre-allocation
- Unlimited number of subdirectories
- Journal checksums

---

### Características del cifrado EFS:

- Enables files to be transparently encrypted to protect confidential data from attackers with physical access to the computer.

---

# Parte 2

### Exchange Server:

Servidor de correo y mensajería, orientado a empresas, comparte agenda y se sincroniza con correos electrónicos, se llamada Microsoft main server.
Tiene seguimiento de trabajo llamado workflow. Ocupa mucho recurso de hardware.
Otro problema es que la base de datos que se acumula es muy intensa, y si le pasa algo a la base de datos, repararla toma mucho tiempo.

---

### SQL Server:

Motor de base de datos que trabaja en base al lenguaje SQL. Motor de base de datos relacional. No era muy popular con las grandes empresas. Creado por syres, comprado por Microsoft.

---

### System Center Configuration Manager:

Software para administrar red por medio de consola, todos los dispositivos que están conectados en una red independiente del SO mediante protocolo SNMP. Hay un control total sobre los equipos en red. También tiene función de Team Viewer. Hace inventario de hardware y software. 
También sirve para saber si falta algo en algún computador con respecto a hardware, de esta forma se puede saber si se perdió o ha sido robado, esto lo anuncia con alertas.
Puede ver si alguien está instalando un software o desintalando.

---

### Forefront Threat Management Gateway (TMG):

Firewall Antivirus, ISA server es como era llamado anteriormente. Tiene protecciones de afuera hacia adentro y protección de a dentro. Analisa paquetes y revisa si algún equipo esta siendo atacado. Tambien puede bloquear palabras y alerta cuando las encuentra.
Permite control total sobre la red.

---

### Microsoft Host Integration Server:

---

### Windows Server Update Services (WSUS):

---

### Microsoft Software Update Services (SUS):

---

### IIS:

---

### Ras:

---

### RRas:

---

### Windows Deployment Services (WDS):

---


---


# Parte 3


### Bosque

Bosque y Arbol están relacionadas al dominio de Active Directory.
Es una colección de uno o más dominios que comparten una misma estructura lógica, catálogo global, esquema y configuración.

Todos los dominios del bosque cuentan con relaciones de confianza automáticas de 2 vías y transitivas.

---

### Árbol

Un árbol de dominios (tree) es una colección de uno o más dominios que comparten un espacio de nombre contiguo. Por ejemplo si el primer dominio se llama contosa.com y tiene un subdominio, este sería subdominio.contosa.com.

---

### Catálogo Global

El Global Catalog (GC) incluye una copia parcial de solo lectura que contiene información de los atributos más utilizados de los objetos del bosque.

Entre otras cosas en lugar de tener que consultar DC por DC de cada dominio (de contar con más de uno) permite acelerar las búsquedas en el bosque consultando directamente al GC ya que tiene información de todos los objetos (funcionando como un índice).

En adición, la membresía de grupos universales se almacena en el Catálogo Global.

---

### Sitio

Los objetos de sitios están ubicados en el contenedor de sitios. Puede usar estos objetos de sitios para realizar las tareas siguientes:
•	Crear nuevos sitios

•	Delegar el control de los sitios mediante la directiva de grupo y los permisos

En todos los sitios, existe un objeto de configuración de sitio NTDS. Este objeto identifica el generador de topología entre sitios (ISTG). El ISTG es el controlador de dominio del sitio que genera objetos de conexión de controladores de dominio en distintos sitios. Además, lleva a cabo las tareas de administración de replicación.

---

### Esquema

Solo existe un maestro de esquema por bosque. Contiene la copia maestra del esquema utilizado por todos los demás controladores de dominio. Tener una copia maestra garantiza que todos los objetos se definan de la misma manera.

---

### Active Directory

Active Directory Domain Services es un servicio de directorio que permite almacenar y administrar información de usuarios, computadoras, impresoras aplicaciones y otros objetos de la red de forma centralizada y segura.

Desde Exchange 2000 Active Directory es el servicio de directorio utilizado por Exchange.

En Active Directory se almacena información de configuración y destinatarios de correo. Cada vez que Exchange requiere información de configuración o sobre algún destinatario consulta Active Directory, si este no se encuentra disponible Exchange no va a funcionar correctamente.

Debido a la fuerte integración de Exchange con Active Directory es importante entender los conceptos más básicos en relación a su interacción con el directorio, donde almacena información y que componentes requiere.

---

### SAM:

Location: C:\Windows\System32\config

Security Account Manager

Es un archivo de base de datos que se encarga
de la autenticacion de inicio de sesion de
cuentas y grupos de trabajo.

En un espacio de trabajo cada maquina guarda
su propio archivo SAM que contiene informacion
sobre todos sus usuarios locales y cuentas grupales.

Las contraseñas de cada usuario se guardan en este archivo
y se les hace un hash para poder minimizar el riesgo a ataques.

### Resumen:

El inicio de sesion local ocurre a traves del archivo SAM.

---

### Servicio miembro:

Member server es un rol definido por Active Directory.

Corre en WIndows 2000 y Windows server 2003.

Pertenece a un dominio, pero no es el controlador de dominio.

Los servicios miembros propician la base de los servicios y aplicaciones
de un dominio.

Contribuye a la seguridad de una red

A member server's key functions include:

* Email management
* Web services
* Faxing
* Image management
* File storage
* Financial application functions
* Human resource functions
* SQL database storage and management

---

### Controlador de Dominio (DC):

Software que responde a los pedidos de autenticacion dentro de una red.

Es el servidor de red que es responsable brindarle recursos del dominio
a los Hosts dentro de la red.

Se encarga de autenticar usuarios, guardar informacion de las cuentas y
hace cumplir las politicas de seguridad de un dominio.

---

### Read Only Domain Controller (RODC):

Se encarga de replicar la configuracion de un Controlador de dominio
a una sucursal remota, esto se hace para que la sucursal principal se
encarge de los cambios del Controlador de Dominios.

Read Only DNS.

Cache de credenciales.

---

### NT4 Primary Domain Controller (PDC)

Con Windows NT4 se tenia un Controlador de Dominios como el principal, a 
este se le denominaba Primary Domain Controller (PDC)

Se dedicaba exclusivamente a servicio de dominios y no usado para
otros servicios como los del Servicio miembro.

Si este fallaba se tenia muchos problemas.

---

### Backup Domain Controller (BDC) 

Puede autenticar usuarios dentro de un dominio,pero todos los cambios debian
ser actualizados mediante el PDC. 

Los cambios se realizan en el PDC para luego ser replicados a los BDC.

Si el PDC fallaba se podia promover alguna BDC a PDC.


---


