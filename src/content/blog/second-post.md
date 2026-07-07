---
title: 'Organización de archivos y directorios en Linux'
description: 'Un recorrido sencillo por la estructura de directorios de Linux: qué es cada carpeta del sistema y para qué sirve.'
pubDate: 'Jul 07 2026'
heroImage: '../../assets/linux.jpg'
---

Cuando empiezas con Linux, una de las primeras cosas que desconcierta es su
estructura de carpetas: `/etc`, `/var`, `/usr`... ¿qué es todo esto? En este post
lo explico de forma sencilla.

## Todo cuelga de la raíz: `/`

En Linux no existen las unidades `C:` o `D:` como en Windows. Todo el sistema parte
de un único punto, la **raíz**, que se representa con una barra: `/`. A partir de
ahí, todo son directorios que cuelgan en forma de árbol.

Además, en Linux **casi todo es un archivo**: los documentos, la configuración e
incluso los dispositivos (como un disco duro) se representan como archivos.

## Esta organización sigue un estándar

No es un caos: la mayoría de distribuciones siguen el **FHS** (*Filesystem
Hierarchy Standard*), una norma que define qué debe ir en cada directorio. Por eso,
una vez lo entiendes en una distribución, te sirve para casi todas.

## Los directorios más importantes

| Directorio | Para qué sirve |
|---|---|
| `/` | La raíz, de donde cuelga todo lo demás. |
| `/etc` | Los archivos de **configuración** del sistema y de los programas. |
| `/home` | La carpeta personal de cada usuario (tus documentos, descargas...). |
| `/root` | La carpeta personal del usuario administrador (`root`). |
| `/var` | Datos **variables**: registros (logs), correos, colas de impresión... |
| `/usr` | Programas y librerías instalados para los usuarios. |
| `/bin` y `/sbin` | **Comandos** esenciales del sistema (los normales y los de administración). |
| `/tmp` | Archivos **temporales**; se suele vaciar al reiniciar. |
| `/opt` | Software adicional u opcional que no viene con la distribución. |
| `/boot` | Los archivos necesarios para **arrancar** el sistema (el kernel, etc.). |
| `/dev` | Los **dispositivos**: discos, USB, teclado... (recuerda, aquí todo es un archivo). |
| `/mnt` y `/media` | Puntos donde se **montan** otros discos o unidades externas. |

## Un par de ejemplos prácticos

- ¿Quieres cambiar la configuración de un servicio? Casi seguro que su archivo está
  en **`/etc`**.
- ¿Algo va mal y quieres ver qué ha pasado? Los registros (logs) suelen estar en
  **`/var/log`**.
- ¿Tus archivos personales? En **`/home/tu-usuario`**.

## Conclusión

La estructura de Linux parece intimidante al principio, pero tiene mucho sentido:
cada cosa tiene su sitio. Saber dónde vive cada tipo de archivo te ahorra tiempo y
te hace moverte por el sistema con mucha más soltura. En próximos posts iré
entrando en algunos de estos directorios con más detalle.