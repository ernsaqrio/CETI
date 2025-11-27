
Hash
- ¿Qué es? Función matemática con un algoritmo (Resumen en n bits y hexadecimal) -> md5,sha1,sha256,sha512.
- Propiedades:
	- Finalista: misma entrada -> misma salida
	- Único: no tiene colisiones
	- Unidireccional: A da B pero con B no sacas A.
	- Pequeños cambios en el input, grandes cambios en el output.
	- Independientemente del tamaño del input, siempre tiene el mismo tamaño el output -> depende el algoritmo de uso (SHA1,SHA256,SHA512)
- ¿Para que sirve?
	- Verifica la integridad y autenticidad del archivo.
	- Antivirus/Firewall/IDS/IPS: mediante el hash. compara ese hash con los hash de virus en una base de datos.
	- Contraseñas: compara el hash guardado con el hash de la contraseña introducida
Cifrar:
- Algoritmo oculto:
	- César
	- Escítala
	- Enigma
- Algoritmo conocido pero claves ocultas:
	- Simétrica: se envía el mensaje con la clave secreta y al recibirlo, si tienes la clave, sacas el mensaje.
		- Es muy rápido.
		- AES
	- Asimétrica: cada uno tiene una clave privada y pública, se envía el mensaje con la pública y con su privada, descifra el mensaje.
		- Es lento.
		- RSA -> Ronald Rivest, Adi Shamir, Leonard Adleman
	- Híbrida: con la clave pública, se cifra la privada para enviarla -> método medio rápido
- Firma dígital:
	- A un archivo le haces el hash (resumen) y eso lo firmas con tu clave publica (obtienes el resumen cifrado) y envías el archivo con el resumen cifrado. El receptor compara 
		