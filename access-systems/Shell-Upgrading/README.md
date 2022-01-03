# Shells

Revisar primero que lenguaje de programacion tiene.

`$ which python`

 Si se encuentra alguna version de Python, pueden usar el siguiente fragmento de codigo...

`$ python3 -c 'import pty;pty.spawn("/bin/bash")'`

De caso contrario si no se encuentra Python, Perl, etc, usar el script para Bash.

`$ /usr/bin/script -qc /bin/bash /dev/null`

Ejemplo:
esto sirve para ejecutar una shell mas interactiva y pasar de esto:
`$ `
a esto:
`www-data@THM-Chal:/home/itguy$  `

# Upgrading 
Escribir lo siguiente dentro de la maquina comprometida:

`$ export TERM=xterm`

Presionamos:

`ctrl + z`

Al final escribimos:

`$ stty raw -echo; fg`

y tendremos una shell aun mas completa.
