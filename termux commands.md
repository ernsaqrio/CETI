Los comandos básicos de Termux incluyen ls para listar archivos, cd para cambiar de directorio, mkdir para crear carpetas, rm para eliminar y apt para gestionar paquetes (como apt update para actualizar y pkg install para instalar). También son útiles clear para limpiar la pantalla, pwd para saber tu ubicación actual, y termux-setup-storage para dar acceso a los archivos del dispositivo. 

**Comandos básicos**

ls: Lista los archivos y directorios en la ubicación actual.
cd <ruta>: Cambia de directorio a la ruta especificada.
pwd: Muestra la ruta completa de tu directorio de trabajo actual.
mkdir <nombre>: Crea una nueva carpeta.
rm <nombre>: Elimina un archivo.
rm -rf <nombre>: Elimina un directorio y su contenido (usa con precaución).
clear: Limpia la pantalla de la terminal.
touch <nombre>: Crea un archivo vacío.
cat <nombre>: Muestra el contenido de un archivo.
echo <texto>: Escribe texto en la pantalla o en un archivo. 

Gestión de paquetes

apt update: Actualiza el índice de paquetes.
apt upgrade: Actualiza todos los paquetes instalados.
pkg install <nombre_paquete>: Instala un paquete específico.
pkg search <nombre_paquete>: Busca un paquete en los repositorios.
pkg uninstall <nombre_paquete>: Desinstala un paquete. 

Acceso y administración de archivos

termux-setup-storage: Da permiso a Termux para acceder al almacenamiento del dispositivo.
cd /sdcard: Navega hasta el directorio de almacenamiento del dispositivo.
cp <origen> <destino>: Copia un archivo o directorio.
mv <origen> <destino>: Mueve o renombra un archivo o directorio.
chmod <permisos> <nombre>: Cambia los permisos de un archivo. 
