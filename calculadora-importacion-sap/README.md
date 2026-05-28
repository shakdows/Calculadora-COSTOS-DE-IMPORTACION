# 🧮 Calculadora de Costo de Importación — SAP B1 + DUA Perú

Calculadora web para calcular el **costo real de importación** de productos basándose en la información del **Precio de Entrega de SAP Business One** y la **DUA (Declaración Única de Aduanas)** de Perú.

## ✨ Funcionalidades

- ✅ Calcula el **Precio Liquidado** (costo final) de cualquier producto importado
- ✅ Descompone el cálculo paso a paso (FOB → CIF → Ad Valorem → Precio Liquidado)
- ✅ Conversión automática a Soles peruanos
- ✅ Tabla de **precios de venta sugeridos** con diferentes márgenes
- ✅ Cálculo con IGV (18%) para precio al público
- ✅ Glosario de términos de comercio exterior
- ✅ 100% responsive (PC, tablet, celular)
- ✅ Sin instalación, sin base de datos, sin servidor — solo HTML/JS

## 🚀 Demo en vivo

👉 **[Ver calculadora en GitHub Pages](https://TU-USUARIO.github.io/calculadora-importacion-sap/)**

*(reemplaza `TU-USUARIO` por tu nombre de usuario de GitHub después de configurar GitHub Pages)*

## 📋 ¿Cómo usar?

1. **Abre la calculadora** en tu navegador
2. Verifica los datos de tu **DUA** y **Costos Fijos** (sección 1 y 2)
3. Ingresa los datos del **producto** que quieres calcular (sección 3)
4. La calculadora muestra automáticamente:
   - El cálculo paso a paso
   - El costo final en US$ y Soles
   - Los precios de venta sugeridos con diferentes márgenes

## 🧮 Fórmulas usadas

```
PRECIO LIQUIDADO = FOB + Flete + Seguro + Gastos CIF + Ad Valorem + Gastos post-CIF
```

### Desglose:
| Componente | Imputación | Fórmula |
|---|---|---|
| FOB línea | Directo | Cantidad × FOB Unitario |
| Flete | Por **PESO** | Peso línea × (Flete Total / Peso Total) |
| Seguro | Por **VALOR** | FOB línea × (Seguro / FOB Total) |
| Gastos CIF base | Por **VALOR** | FOB línea × ((Agente + Almacenaje + G.Origen) / FOB Total) |
| Ad Valorem | Sobre **CIF** | CIF línea × (Ad Valorem / CIF Total) |
| Gastos post-CIF | Por **VALOR** | FOB línea × ((Handling + Pickup + Transporte) / FOB Total) |

## 🌐 Cómo publicar tu propia copia en GitHub Pages

### Opción A — Desde la web (más fácil, sin instalar nada)

1. **Crea una cuenta en GitHub** (gratis): https://github.com/signup
2. Click en **"+"** → **"New repository"**
3. Nombre del repo: `calculadora-importacion-sap` (o el que quieras)
4. Marca **"Public"** y haz click en **"Create repository"**
5. En el repo nuevo, click en **"uploading an existing file"**
6. **Arrastra** los archivos `index.html` y `README.md`
7. Click en **"Commit changes"**
8. Ve a **Settings → Pages** (en el menú lateral)
9. En "Source" selecciona **Deploy from a branch** → **main** → **/(root)** → **Save**
10. Espera ~1 minuto. Tu sitio estará en: `https://TU-USUARIO.github.io/calculadora-importacion-sap/`

### Opción B — Desde la terminal (si conoces Git)

```bash
git clone https://github.com/TU-USUARIO/calculadora-importacion-sap.git
cd calculadora-importacion-sap
# copia index.html y README.md al directorio
git add .
git commit -m "Initial commit"
git push origin main
```

Luego activa GitHub Pages desde Settings → Pages.

## 📁 Estructura del proyecto

```
calculadora-importacion-sap/
├── index.html          ← La calculadora (todo en un archivo)
├── README.md           ← Este archivo
└── excel/
    └── Calculadora.xlsx ← Versión Excel (opcional)
```

## ⚠️ Disclaimer

Esta calculadora usa la **metodología estándar internacional** de prorrateo (DUA SUNAT). SAP Business One puede mostrar valores ligeramente diferentes por configuraciones internas específicas. Los resultados aquí son una **aproximación cercana** (±3-5%). Para valores oficiales, usa siempre el "Precio Liquidado" de SAP B1.

## 🛠️ Personalización

Para personalizar la calculadora:

- **Cambiar valores por defecto:** Edita los `value="..."` en los `<input>` del HTML
- **Agregar márgenes:** Edita el array `margenes` en el JavaScript (línea ~XXX)
- **Cambiar colores:** Modifica las variables CSS al inicio del `<style>`

## 📞 Contacto / Soporte

Si tienes preguntas o sugerencias, puedes:
- Abrir un [Issue](https://github.com/TU-USUARIO/calculadora-importacion-sap/issues) en GitHub
- Hacer un Fork del proyecto y enviar un Pull Request

## 📄 Licencia

MIT License — Úsalo, modifícalo y compártelo libremente.

---

⭐ Si te resultó útil, dale una **estrella** al repo en GitHub!
