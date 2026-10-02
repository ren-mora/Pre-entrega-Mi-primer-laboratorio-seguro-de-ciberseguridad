**Reporte Técnico de Configuración de Laboratorio \- Renzo Nicolás Mora**

**Windows:**

1. Cree un nuevo usuario llamado "UsuarioSeguro" y me asegure de que el tipo de cuenta sea "Usuario estándar" y no Administrador. La idea sería usar este usuario para las tareas diarias y solo usar la clave admin cuando el sistema lo pida.

<img width="628" height="341" alt="image7" src="https://github.com/user-attachments/assets/ae5d54f5-8672-4bd7-a41c-da9ed6a8753c" />

2. En Windows Update le di clic a "Buscar actualizaciones" y se puso a descargar las últimas actualizaciones de seguridad, ya figura como "Actualizado". Esto se realiza para garantizar que los agujeros de seguridad que Windows ya conoce estén protegidos o solucionados.

<img width="644" height="355" alt="image6" src="https://github.com/user-attachments/assets/7e7a3471-638a-453e-96eb-795048434b89" />

3. Abrí el ítem de  "Activar o desactivar las características de Windows", buscando en la lista la opción: "Compatibilidad con el protocolo para compartir archivos SMB 1.0/CIFS". La desmarque y reinicie Windows. Esto es porque SMBv1 es un protocolo obsoleto e inseguro que no tiene cifrado moderno ni mecanismos robustos de integridad. Fue la razón principal de los ataques masivos de ransomware WannaCry y NotPetya, al deshabilitarlo se reduce drásticamente la superficie de ataque.

<img width="410" height="364" alt="image2" src="https://github.com/user-attachments/assets/6352270d-6658-43cd-a213-37d9cfaf7851" />

**Linux**

1. En las opciones de VirtualBox, configure la tarjeta de red de la máquina virtual conectada a NAT ya que en este modo la máquina virtual no obtiene una dirección IP visible ni accesible directamente desde la red local física externa. Esto hace que bloquee intentos de conexión o escaneos no solicitados desde otros dispositivos de la red física.

<img width="568" height="411" alt="image1" src="https://github.com/user-attachments/assets/182a1478-d9e1-4a71-9bc3-009cc6a56035" />

2. Ejecuté el comando “sudo apt update” en la terminal para actualizar la lista local de paquetes disponibles y sus versiones con repositorios oficiales de Kali Linux. Es importante su uso recurrente ya que permite al sistema enterarse si los paquetes instalados tienen versiones más recientes que tengan soluciones a fallos de seguridad o vulnerabilidades conocidas. Es el paso previo y obligatorio antes de instalar parches mediante el “apt upgrade”.

<img width="644" height="207" alt="image8" src="https://github.com/user-attachments/assets/a20cf03c-3d3e-4de5-983c-1e343d1d9a3f" />

3. Revise los permisos del archivo example\_file.txt ya que auditar los permisos en Linux garantiza que archivos sensibles no queden expuestos con permisos de escritura o ejecución, mitigando riesgos de manipulación de datos o escalada de privilegios.

<img width="644" height="207" alt="image3" src="https://github.com/user-attachments/assets/824a639b-6da6-4952-a283-0b12b7fd8df3" />

4. Cree un usuario seguro y comprobé los permisos asignados al mismo confirmando que el usuario no forma parte de grupos privilegiados (como sudo, wheel o root). Esto garantiza que se pueda usar ese usuario para operar estrictamente de forma restringida, evitando ejecuciones no autorizadas de comandos administrativos en Linux.  

<img width="644" height="207" alt="image4" src="https://github.com/user-attachments/assets/0571a3b6-6a7a-4338-9818-722c540a11e0" />
     
5. Realice un snapshot capturando el estado exacto del disco y la configuración de la máquina virtual justo después de completar las configuraciones seguras, actualizaciones y pruebas. El snapshot funciona como un plan de contingencia inmediato restaurando la operatividad. Además, si en el futuro ejecutase software sospechoso, la snapshot permite descartar cambios con un retorno al estado previo.

<img width="912" height="188" alt="image5" src="https://github.com/user-attachments/assets/20268eb4-6b28-4367-9d49-558e5597544b" />
