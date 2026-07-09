---
title: 'Chuleta de OSINT: operadores y comandos esenciales'
description: 'Recopilación práctica de operadores de búsqueda y comandos útiles para OSINT: Google dorks, WHOIS, DNS, metadatos y más.'
pubDate: 'Jul 09 2026'
heroImage: '../../assets/osint.jpg'
tags: ['osint', 'seguridad']
---

Esta es una chuleta rápida con los "códigos" que más se usan en OSINT: operadores de
búsqueda y comandos de terminal. La idea es tenerlos todos a mano en un solo sitio.

> ⚠️ **Recordatorio:** usa esto solo sobre información **pública** y con fines
> **legales y éticos** (auditorías con permiso, CTFs, proteger tu propia huella o
> aprender). Nunca para acceder a sistemas ajenos ni perjudicar a nadie.


## 🔎 Google Dorks (operadores de búsqueda)

```text
site:ejemplo.com              Resultados solo de ese dominio
filetype:pdf                  Solo archivos de ese tipo (pdf, xls, docx...)
intitle:"index of"            Busca esa frase en el título de la página
inurl:admin                   La palabra aparece en la URL
intext:"contraseña"           La palabra aparece en el cuerpo del texto
cache:ejemplo.com             Versión cacheada por Google
"frase exacta"                Busca la frase literal
palabra1 OR palabra2          Una u otra (también con | )
compras -tienda               Excluye resultados con esa palabra
```

Se pueden **combinar** para afinar mucho:

```text
site:ejemplo.com filetype:pdf intext:"confidencial"
```

## 🌐 WHOIS y DNS

```bash
whois ejemplo.com             Quién registró el dominio y datos asociados
dig ejemplo.com               Registros DNS del dominio
dig +short ejemplo.com        Igual, pero solo el resultado limpio
dig ejemplo.com MX            Servidores de correo
dig ejemplo.com TXT           Registros TXT (SPF, verificaciones...)
dig ejemplo.com NS            Servidores de nombres
dig -x 8.8.8.8                DNS inverso (de IP a nombre)
host ejemplo.com              Resolución rápida
nslookup ejemplo.com          Alternativa clásica a dig
```

## 🧩 Subdominios y certificados

```text
# Certificados públicos (revela subdominios). Se consulta en el navegador:
https://crt.sh/?q=%25.ejemplo.com
```

```bash
# Recopila correos y subdominios de un dominio
theHarvester -d ejemplo.com -b all
```

## 🖼️ Metadatos de archivos e imágenes

```bash
exiftool foto.jpg             Muestra TODOS los metadatos
exiftool -gps:all foto.jpg    Solo los datos de GPS (ubicación)
exiftool -all= foto.jpg       Elimina los metadatos (útil para protegerte)
```

## 👤 Nombres de usuario y correos

```bash
sherlock nombreusuario        Busca ese alias en decenas de redes
```

```text
# Comprobar si tu correo aparece en filtraciones (en el navegador):
https://haveibeenpwned.com
```

## 🛰️ Shodan (dispositivos conectados)

```text
hostname:ejemplo.com          Dispositivos de ese dominio
port:22                       Filtra por puerto
country:ES                    Filtra por país
org:"Nombre Empresa"          Filtra por organización
product:nginx                 Filtra por software detectado
```

## 🕰️ Ver versiones antiguas de una web

```text
# Archivo histórico (Wayback Machine), en el navegador:
https://web.archive.org/web/*/ejemplo.com
```

## Conclusión

Con estos operadores y comandos ya puedes hacer un reconocimiento básico de forma
totalmente legal. Mi recomendación para practicar: aplícalos sobre ti mismo o
sobre tu propio dominio, así aprendes la técnica y de paso ves qué información
tuya está expuesta.