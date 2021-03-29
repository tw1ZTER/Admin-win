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

### FAT16:

- File Allocation Table 16 bits
- The configuration files of every sector are expressed by 16 bytes in FAT16 and this is why it is named FAT16

### FAT32:

- File Allocation Table 32 bits
- Maximum file size is only around 4 gigabytes.
- Maximum size of a FAT32 partition is around 2 terabytes.

### VFAT:

- Virtual File Allocation Table
- Extension of the FAT file system and was introduced with Windows 95

### exFat:

- Introduced by Microsoft in 2006
- Optimized for flash memory such as USB flash drives and SD cards.
- exFAT can be used where NTFS is not a feasible solution.

### NTFS:

- New Technology File System.
- File-level encryption called the Encrypting File System (EFS)

### EXT3:

- Third extended filesystem
- Journaled file system that is commonly used by the Linux kernel. (Journaled file system: keeps track of changes not yet committed to the file system's main part by recording the intentions of such changes in a data structure known as a "journal")

### EXT4:

- Backward-compatible with ext3.
- Large file system:
    - support volumes with sizes up to 1 exbibyte (EiB) and single files with sizes up to 16 tebibytes (TiB)
- Persistent pre-allocation
- Unlimited number of subdirectories
- Journal checksums

### Características del cifrado EFS:

- Enables files to be transparently encrypted to protect confidential data from attackers with physical access to the computer.

# Parte 2

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

