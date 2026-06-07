# Laboratorio Clínico Microbiología Barinas

Landing page oficial + encuesta de experiencia Sede Centro.

**Stack:** GitHub Pages · Google Apps Script · Google Sheets  
**Costo:** $0 — completamente gratuito  
**Elaborado por:** [Marklife Agency](https://www.instagram.com/marklifeagency) · (0424) 545 7065

---

## Estructura del repositorio

```
/
├── index.html              ← Landing page principal
├── encuesta/
│   └── index.html          ← Sublanding encuesta Sede Centro
├── apps-script/
│   └── Code.gs             ← Backend Google Apps Script
└── README.md
```

---

## ⚙️ Configuración inicial (hacer UNA sola vez)

### PASO 1 — Activar GitHub Pages

1. Ve a tu repo en GitHub → **Settings**
2. Sidebar izquierdo → **Pages**
3. Source: **Deploy from a branch**
4. Branch: `main` · Folder: `/ (root)`
5. Clic en **Save**
6. En ~2 minutos tu sitio estará en:  
   `https://TU-USUARIO.github.io/microbiologia-barinas/`

---

### PASO 2 — Crear Google Sheet (base de datos)

1. Ve a [sheets.google.com](https://sheets.google.com)
2. Crea una hoja nueva → nómbrala **"Encuesta Microbiología Barinas"**
3. Copia el **ID** de la URL:  
   `https://docs.google.com/spreadsheets/d/`**`ESTE-ES-EL-ID`**`/edit`
4. Guárdalo, lo necesitas en el Paso 3

---

### PASO 3 — Crear el backend (Apps Script)

1. Ve a [script.google.com](https://script.google.com)
2. Clic en **"Nuevo proyecto"**
3. Borra todo el contenido del editor
4. Pega el contenido de `apps-script/Code.gs`
5. En la línea 29, reemplaza `PEGAR_ID_DE_TU_GOOGLE_SHEET_AQUI` con el ID del Paso 2:
   ```javascript
   var SPREADSHEET_ID = '1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgVE2upms';
   ```
6. Guarda el proyecto (Ctrl+S) → ponle nombre: **"Encuesta Microbiología"**

---

### PASO 4 — Desplegar el Apps Script como API

1. Clic en **"Desplegar"** → **"Nueva implementación"**
2. Clic en el ícono ⚙️ → selecciona **"Aplicación web"**
3. Configura:
   - **Descripción:** `v1`
   - **Ejecutar como:** `Yo (tu-correo@gmail.com)`
   - **Quién tiene acceso:** `Cualquier persona`
4. Clic en **"Desplegar"**
5. Autoriza los permisos cuando te lo pida (es tu propio script)
6. **Copia la URL** que aparece — se ve así:
   ```
   https://script.google.com/macros/s/AKfycbx.../exec
   ```

---

### PASO 5 — Conectar la encuesta con el backend

1. Abre `encuesta/index.html` en tu editor de texto
2. Busca la línea 252 (o busca `REEMPLAZAR_CON_TU_URL`):
   ```javascript
   var SCRIPT_URL = 'REEMPLAZAR_CON_TU_URL_DE_APPS_SCRIPT';
   ```
3. Reemplaza con tu URL del Paso 4:
   ```javascript
   var SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbx.../exec';
   ```
4. Guarda el archivo
5. Haz commit y push al repositorio

---

### PASO 6 — Verificar que todo funciona

1. Abre: `https://TU-USUARIO.github.io/microbiologia-barinas/encuesta/`
2. Responde la encuesta de prueba
3. Abre tu Google Sheet → deberías ver la respuesta en la hoja **"Respuestas"**

---

### PASO 7 — (Opcional) Probar el backend directamente

En Apps Script, ejecuta la función `testInsert()` manualmente:
1. En el editor de Apps Script, selecciona `testInsert` en el dropdown
2. Clic en ▶ Ejecutar
3. Abre tu Sheet → debe aparecer una fila de prueba

---

## Compartir la encuesta en WhatsApp o Instagram

**URL directa de la encuesta:**
```
https://TU-USUARIO.github.io/microbiologia-barinas/encuesta/
```

Puedes compartirla:
- Como link en Instagram Stories con sticker de enlace
- En el caption de posts
- Por WhatsApp directo a pacientes
- Como QR en la sala de espera de Sede Centro

---

## Ver resultados

1. Abre [Google Sheets](https://sheets.google.com)
2. Abre **"Encuesta Microbiología Barinas"**
3. Hoja **"Respuestas"** → todas las respuestas con timestamp automático

Los datos llegan en tiempo real, con formato de colores aplicado automáticamente.

---

## Actualizar la landing page

1. Edita `index.html` localmente
2. `git add . && git commit -m "Actualización landing" && git push`
3. GitHub Pages se actualiza automáticamente en ~1 minuto

---

## Soporte

**Marklife Agency** · (0424) 545 7065  
marklifeworkers@gmail.com · [@marklifeagency](https://instagram.com/marklifeagency)
