# 💰 Finanzas Web

App de gestión financiera familiar hecha en HTML puro — sin frameworks, sin dependencias, sin servidor. Solo descarga el archivo y ábrelo en tu navegador.

## ✨ Funcionalidades

- **Inicio** — resumen general del balance, ingresos y gastos de la semana, y barras de progreso por categoría (Gastos, Préstamos, Créditos, Kash)
- **Registrar** — registra movimientos de tipo Ingreso, Gasto Personal, Crédito bancario o Kash; también permite transferencias entre cuentas (Efectivo / Bancos)
- **Movimientos** — historial filtrable por tipo y semana
- **Tiendas** — seguimiento de gastos por tienda o comercio
- **Préstamos** — registro y control de préstamos con cuotas
- **Reporte** — vista semanal/mensual/anual con desglose de ingresos, gastos del negocio, gastos de casa y resumen final

## 🚀 Uso rápido

1. Descarga el archivo `Finanzas.html`
2. Ábrelo en cualquier navegador moderno
3. Empieza a registrar tus movimientos

Los datos se guardan automáticamente en el `localStorage` de tu navegador. No se envía nada a ningún servidor.

## 🔧 ¿Cómo conectarlo a una base de datos?

Actualmente la app usa `localStorage` para persistir los datos. Si quieres conectarla a una BD real, reemplaza las siguientes funciones en el script:

| Función actual | Qué hace | Qué reemplazar |
|---|---|---|
| `loadMovs()` | Carga movimientos desde localStorage | Fetch a tu API GET /movimientos |
| `saveMovs()` | Guarda movimientos en localStorage | Fetch a tu API POST /movimientos |
| `loadTraspasos()` | Carga transferencias | Fetch a tu API GET /traspasos |
| `saveTraspasos()` | Guarda transferencias | Fetch a tu API POST /traspasos |
| `loadPrestamos()` | Carga préstamos | Fetch a tu API GET /prestamos |
| `savePrestamos()` | Guarda préstamos | Fetch a tu API POST /prestamos |

Ejemplo de cómo quedaría `loadMovs()` con una API REST:

```javascript
async function loadMovs() {
  const res = await fetch('https://tu-api.com/movimientos');
  movs = await res.json();
}
```

## 🛠️ Tech stack

- HTML5 + CSS3 + JavaScript vanilla
- Fuentes: [Sora](https://fonts.google.com/specimen/Sora) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (Google Fonts)
- Persistencia: `localStorage` (sin BD por defecto)

## 📄 Licencia

MIT — úsalo, modifícalo y compártelo libremente.
