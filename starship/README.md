## Starship

Archivos de configuración para la modificación del prompt estándar de bash, que se puede bajar desde [https://starship.rs/](https://starship.rs/).
La instalación es bastante sencilla, solo necesitamos tener instalado `curl`.

### Instalar `curl`

En caso de no tener instalado el paquete de `curl`, el lo podemos instalar de la siguiente manera desde la terminal:

**OS basados en Redhat**
`sudo yum install -y curl`

**OS basados en Debian**
`sudo apt install -y curl`

Una vez instalado el paquete `curl` solo debemos ejecutar el siguiente comando desde la terminal:
`curl -sS https://starship.rs/install.sh | sh`

Durante el proceso de instalación va a pedir tu contraseña, ya que debe ejecutarse como root.

Para mas referencias de como instalarlo, lo mejor es ir a la fuente [https://starship.rs/](https://starship.rs/).

Al final la instalación solo queda instanciar `starship` cuando abrimos una terminal.
Para esto debemos agregar esta linea `eval "$(starship init bash)"` al final del archivo `~/.bashrc` utilizando el editor que mas nos guste.


## starship/config/starship.toml

Este es el archivo de configuración de `starship`, donde definimos formatos de salida en pantalla para el `prompt` del sistema y el mismo se debe copiar al directorio: `~/.config` en el home del usuario.

Por ejemplo, si tu usuario es `cyberzoo`, entonces el archivo se debería copiar al destino `/home/cyberzoo/.config/starship.toml`.

Si no sabes cual es tu `home`, entonces podes ejecutar `echo ~` en tu terminal, y esto te va a mostrar cual es el directorio `home` de tu usuario.

`Starship` nos mostrará un prompt diferente dependiendo del contenido del directorio donde estemos parados.

Para definir que queremos que `starship` muestre, entonces editamos este archivo.

Esta es la configuración que uso actualmente.

## starship/.starshiprc

Archivo donde se declaran variables que podemos llegar a utilizar para la configuración de `starship`.

Este archivo debe ir en el raíz del usuario, típicamente `/home/usuario/.startshiprc`, reemplazando `usuario` por el nombre de usuario actual. 

En la sección anterior se puede ver como saber cual es la ruta al home de tu usuario.

Para aplicar esta configuración cada vez que iniciamos una consola, editamos el archivo `.bashrc`, en la raíz del usuario y agregamos lo siguiente al final, antes de `eval "$(starship init bash)"`.

Nos quedaría algo mas o menos asi:

```
$ vim .bashrc
[...]
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
export SSLKEYLOGFILE=~/.ssl-key.log

source ~/.starshiprc
eval "$(starship init bash)"
```