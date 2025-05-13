# k6 - Flujo de Compra como Invitado (mac.js)

Este proyecto automatiza el flujo de compra como invitado en [maconline.com](https://www.maconline.com) usando **k6/browser**.

---

## 🚀 Ejecución Básica

Para ejecutar el script y ver el resultado en la consola:

```bash
k6 run mac.js
```

Esto mostrará en la terminal los checks principales y el resumen de la ejecución.

---

## 📊 Ejecución con Reporte (Archivos)

### 1. **Reporte JSON**

Guarda los resultados de la ejecución en un archivo JSON:

```bash
k6 run mac.js --out json=resultado.json
```

- El archivo `resultado.json` contendrá todos los datos de la ejecución.
- Útil para análisis posterior o generación de reportes HTML.

---

### 2. **Reporte CSV**

Guarda los resultados en formato CSV:

```bash
k6 run mac.js --out csv=resultado.csv
```

- El archivo `resultado.csv` puede abrirse en Excel o Google Sheets para análisis tabular.

---

### 3. **Reporte HTML (usando k6-reporter)**

k6 no genera HTML directamente, pero puedes convertir el JSON a HTML usando [k6-reporter](https://github.com/benc-uk/k6-reporter):

#### **Pasos:**

1. Ejecuta y guarda el resultado en JSON:
    ```bash
    k6 run mac.js --out json=resultado.json
    ```

2. Instala k6-reporter (requiere Node.js):
    ```bash
    npm install -g k6-reporter
    ```

3. Genera el HTML:
    ```bash
    k6-reporter --out resultado.html resultado.json
    ```

- El archivo `resultado.html` será un reporte visual y navegable.

---

### 4. **Guardar el resumen de consola en un archivo de texto**

Si solo quieres guardar el resumen que ves en la consola:

```bash
k6 run mac.js > reporte.txt
```

---

## 📝 Ejemplo de Ejecución Completa

```bash
# Solo consola
k6 run mac.js

# Guardar en JSON
k6 run mac.js --out json=resultado.json

# Guardar en CSV
k6 run mac.js --out csv=resultado.csv

# Generar HTML (requiere k6-reporter)
k6 run mac.js --out json=resultado.json
k6-reporter --out resultado.html resultado.json
```

---

## 📈 ¿Qué información contienen los reportes?

- **Checks**: Resultado de cada paso clave del flujo (éxito/fallo).
- **Web Vitals**: Métricas de rendimiento (LCP, FCP, CLS, etc.).
- **HTTP Requests**: Tiempos y errores de las peticiones de red.
- **Duración total**: Tiempo que toma completar el flujo.
- **Datos transferidos**: Volumen de datos enviados y recibidos.

---

## 🛠️ Requisitos

- [k6](https://k6.io/docs/getting-started/installation/)
- (Opcional para HTML) [Node.js](https://nodejs.org/) y [k6-reporter](https://github.com/benc-uk/k6-reporter)

---

## 📚 Recursos

- [Documentación oficial de k6](https://k6.io/docs/)
- [k6 Browser Docs](https://grafana.com/docs/k6/latest/using-k6-browser/)
- [k6-reporter](https://github.com/benc-uk/k6-reporter)

---

## 📝 Notas

- Puedes modificar el script `mac.js` para adaptarlo a otros flujos o agregar más checks.
- Para pruebas de carga, ajusta los valores de `vus` e `iterations` en la sección `options` del script.

---

