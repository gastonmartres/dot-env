### Archivos dot-env y scripts en bash

## .historyrc

Archivo con definiciones para el historial de comandos que me parece son útiles.

Para invocarlo, el archivo debe residir en el `home` del usuario y agregar la llamada en el archivo `.bashrc`.

Esto quedaría mas o menos así:

```
$ vim ~/.bashrc
[...]
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
export SSLKEYLOGFILE=~/.ssl-key.log

source ~/.historyrc
```