# Apps Script — TRIB & TRIP Formación
## Instrucciones de configuración (10 minutos)

---

### PASO 1 — Preparar Google Drive

1. En tu Google Drive crea una carpeta llamada **"Alumnos"**
2. Abre la carpeta → copia el ID de la URL:
   `https://drive.google.com/drive/folders/`**ESTE_ES_EL_ID**
3. Guárdalo, lo necesitarás en el Paso 3

---

### PASO 2 — Crear la Google Sheet

1. Ve a [sheets.google.com](https://sheets.google.com) → crea una hoja nueva
2. Llámala **"TRIB & TRIP Formación — Diagnósticos"**
3. Copia el ID de la URL:
   `https://docs.google.com/spreadsheets/d/`**ESTE_ES_EL_ID**`/edit`
4. Guárdalo

---

### PASO 3 — Crear el Apps Script

1. Ve a [script.google.com](https://script.google.com) → **"Nuevo proyecto"**
2. Llámalo **"TRIB & TRIP Formación"**
3. Borra todo el código que viene por defecto
4. Pega el contenido del archivo **Code.gs**
5. Rellena la sección CONFIG con tus datos:

```javascript
const CONFIG = {
  EMAIL_DESTINO:    'pere@tudominio.com',      // ← Tu email real
  SHEET_ID:         'ABC123...',               // ← ID de la Sheet del Paso 2
  CARPETA_RAIZ_ID:  'XYZ456...',              // ← ID de la carpeta del Paso 1
  NOMBRE_HOJA:      'Diagnósticos'
};
```

---

### PASO 4 — Publicar como Web App

1. En el editor → **Implementar → Nueva implementación**
2. Tipo: **Aplicación web**
3. Ejecutar como: **Yo (tu cuenta)**
4. Acceso: **Cualquier usuario** ← importante para que el formulario pueda llamarlo
5. Clic en **Implementar**
6. Copia la **URL de la aplicación web** que te da → la necesitas en el formulario

---

### PASO 5 — Conectar el formulario

En el código HTML del formulario (index.html), busca esta línea:

```javascript
const APPS_SCRIPT_URL = 'TU_URL_APPSCRIPT_AQUI';
```

Y sustitúyela por la URL del Paso 4.

---

### PASO 6 — Permisos (solo la primera vez)

La primera vez que se ejecute el script, Google te pedirá autorizar permisos para:
- Leer/escribir en Google Sheets
- Crear archivos en Drive
- Enviar emails con Gmail

Acepta todos. Son permisos para tu propia cuenta.

---

### RESULTADO FINAL

Cuando un alumno envíe el formulario:

✅ Fila nueva en Google Sheet con todos los datos  
✅ Carpeta creada en Drive → Alumnos → [Nombre alumno] → Diagnóstico [fecha]  
✅ Google Doc formateado guardado en esa carpeta  
✅ Email en tu bandeja con resumen + enlace al Doc  

