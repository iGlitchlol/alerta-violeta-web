# Alerta Violeta Colima: página web y API

> Este proyecto tiene dos partes: la **página web + API** (este repo) y la **app móvil** en Flutter: [alerta-violeta-app](https://github.com/iGlitchlol/alerta-violeta-app).

Panel web de estadísticas y API REST para los reportes de incidentes de violencia de género enviados desde la app Alerta Violeta Colima.

**Sitio en vivo:** https://verduzco2.vercel.app

## Página web (`index.html`)

- Gráfica de barras con los reportes por zona.
- Gráfica de dona con los tipos de violencia reportados.
- Lista de reportes con su ubicación en un mapa.

Hecha con HTML, CSS, JavaScript y [Chart.js](https://www.chartjs.org/).

## API (`api/report.js`)

Función serverless en Vercel (Node.js).

| Método | Ruta          | Descripción                     |
|--------|---------------|---------------------------------|
| POST   | `/api/report` | Guarda un reporte nuevo         |
| GET    | `/api/report` | Devuelve todos los reportes     |

Ejemplo de reporte (lo que envía la app):

```json
{
  "lat": 19.2433,
  "lng": -103.7250,
  "fecha": "2026-03-20 17:45:00",
  "categoria": "Acoso",
  "descripcion": "Texto del reporte",
  "foto": "<imagen en base64, opcional>"
}
```

> Los reportes se guardan en memoria, así que se borran cuando Vercel reinicia la función. Para producción haría falta conectar una base de datos.

## Correr en local

```bash
npm i -g vercel
vercel dev
```
