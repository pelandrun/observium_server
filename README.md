# observium
Esta es una copia mala de este https://github.com/somsakc/docker-observium/ buen proyecto.

El propósito de esta copia es solucionar un problema que me dió bastantes dolores de cabeza, el timezone. Del lado del observium todo andaba bien, logs, alerta y calendario, sin embargo los rrdtool generaba los gráficos en UTC, la solución, quiza burda fue crear al momento de instanciar el container de observium, un link del archivo /etc/localtime con el archivo correspondiente. Para esto modifique el archivo observium/observium-init.sh insertando al final esta línea

/usr/bin/ln -sf  "/usr/share/zoneinfo/$TZ" /etc/localtime

Al mismo servicio se agregó un nginx proxy manager.

Es necesario crear la red para el servicio o modificar yml en consecuencia.
docker network create servers1_net

