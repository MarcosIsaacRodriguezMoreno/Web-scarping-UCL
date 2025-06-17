# ⚽ Web Scraping de Partidos de la UEFA Champions League por Temporada

Este proyecto realiza un scraping automatizado de los datos de partidos de la UEFA Champions League (UCL) para una temporada específica.

El script accede a la página oficial de la UEFA, extrae los enlaces de todos los partidos jugados en esa temporada y obtiene estadísticas clave de cada encuentro, generando como resultado un DataFrame consolidado con los datos del equipo local y del visitante.
## 📦 Requisitos

Antes de ejecutar el script, asegúrate de tener instaladas las siguientes herramientas y librerías:

- [Python 3.10+](https://www.python.org/)
- [Google Chrome](https://www.google.com/chrome/)
- [ChromeDriver](https://sites.google.com/chromium.org/driver/) (compatible con tu versión de Chrome)
- Paquetes de Python:
  - `selenium`
  - `polars`

Puedes instalar las librerías necesarias ejecutando el siguiente comando:

```bash
pip install selenium polars
```

## 🛠️ Instalación

1. Clona este repositorio en tu máquina local:

```bash
git clone https://github.com/MarcosIsaacRodriguezMoreno/Web-scarping-UCL
cd Web-scarping-UCL
```
2. Instala las dependencias necesarias:
```bash
pip install selenium polars
```
## 🚀 Uso

1. Abre el archivo Python y edita la variable `season` para indicar el año de la temporada que deseas analizar:

```python
season = 2024
```

2. Luego ejecuta el script desde jupyter.

3. Entrará a la página oficial de la UEFA Champions League.

- Aceptará cookies y navegará a la sección de partidos.

- Realizará scroll para cargar todos los partidos de la temporada.

- Extraerá los enlaces de los partidos.

- Visitará cada enlace para obtener estadísticas de juego.

- Procesará los datos y construirá dos DataFrames con polars: uno para el equipo local y otro para el visitante.

- Finalmente, unificará ambos en un solo DataFrame llamado season_stats.

4. Al finalizar, se imprimirá en consola la cantidad de partidos encontrados y un mensaje de cierre exitoso del scraping.

## 📊 Estructura de los Datos

El resultado final del script es un `DataFrame` llamado `season_stats` construido con la librería `polars`.

Este `DataFrame` contiene:

- Estadísticas del **equipo local** con sufijo `_local`
- Estadísticas del **equipo visitante** con sufijo `_visit`
- El nombre de cada equipo al inicio de las columnas

Las columnas representan métricas como:

- Posesión
- Tiros al arco
- Faltas
- Goles
- Tarjetas
- Y otras estadísticas clave provistas por UEFA

Cada fila representa un partido de la temporada seleccionada.

## 📌 Notas adicionales

- Este script está diseñado para funcionar con la estructura actual de la página de la UEFA.  
  Si el sitio web cambia su diseño o clases CSS, el script podría requerir ajustes.

- El scraping puede tardar varios minutos dependiendo de la cantidad de partidos en la temporada y la velocidad de tu conexión a internet.

- El navegador se abrirá en pantalla (modo visible). Puedes modificar el script para usar modo **headless** si lo deseas.

- Se utiliza `ThreadPoolExecutor` para paralelizar la descarga de estadísticas, aprovechando la capacidad de tu CPU.

- Asegúrate de tener `chromedriver` actualizado y en tu variable de entorno `PATH`.

- Las estadísticas pueden variar en disponibilidad dependiendo del partido (por ejemplo, partidos cancelados o sin datos).


