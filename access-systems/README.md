#Buscar capabilities

`$ getcap -r / 2>/dev/null`


#Remover capabilities

`$ getcap -r /usr/bin/python3.8`


#Verificar si tiene capabilitie

`$ getcap /usr/bin/python3.8`


#Crear capabilitie

`$ setcap -r /usr/bin/python3.8`
