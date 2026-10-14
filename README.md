# Luma Finanzas | UVEG · Unidad 2 · Reto 2

Luma Finanzas es una aplicación web responsiva para la administración de finanzas personales. Permite registrar ingresos y gastos, consultar movimientos, gestionar presupuestos y dar seguimiento a suscripciones.

## Funcionalidades

- Panel con saldo, ingresos, gastos y visualización por categoría.
- Registro, edición y eliminación de movimientos.
- Búsqueda, filtros y exportación de movimientos a CSV.
- Presupuestos por categoría y seguimiento de límites.
- Administración de suscripciones.
- Persistencia de datos en el navegador mediante `localStorage`.
- Datos ficticios para demostración.

## Estructura

```text
fuente/
  index.html
  css/styles.css
  js/app.js
  img/favicon.svg
produccion/
  index.html
  css/styles.min.css
  js/app.min.js
  img/favicon.svg
apache/luma.conf
README.md
.gitignore
```

## Optimización

Los archivos HTML, CSS, JavaScript e imágenes se organizan en carpetas separadas. Los archivos CSS y JavaScript de producción se generan con `clean-css-cli` y `terser`.

```powershell
npm.cmd install --save-dev terser clean-css-cli
npx.cmd cleancss -o produccion/css/styles.min.css fuente/css/styles.css
npx.cmd terser fuente/js/app.js --compress --mangle --output produccion/js/app.min.js
```

El contenido de `produccion/` se comprime como `Luma_Finanzas_Produccion.zip` para su despliegue.

## Versionamiento

El proyecto se administra con Git y se publica en GitHub. Los commits identifican el código fuente, la optimización y la configuración del servidor.

## Despliegue en Apache (Windows)

Ruta local del proyecto:

```text
C:\Users\USER\Desktop\Luma_Finanzas_Reto2\Luma_Finanzas_Reto2
```

Directorio servido:

```text
C:/Users/USER/Desktop/Luma_Finanzas_Reto2/Luma_Finanzas_Reto2/produccion
```

En `C:/xampp/apache/conf/httpd.conf`, habilitar una única directiva `Listen 8080` y `Include conf/extra/httpd-vhosts.conf`. Colocar el contenido de `apache/luma.conf` en `C:/xampp/apache/conf/extra/httpd-vhosts.conf` y reiniciar Apache.

Verificación:

```powershell
& "C:\xampp\apache\bin\httpd.exe" -t
```

Dirección de acceso: `http://localhost:8080/`.

## Alcance

Prototipo académico de uso local. No conecta cuentas bancarias, no permite operaciones bancarias y no sincroniza datos entre dispositivos. Los registros se almacenan en el navegador.
