# Mis Reuniones · v2

Aplicación de un solo archivo para gestionar reuniones internacionales con conversión automática de zona horaria a España. Rediseñada con una estética editorial-SaaS (Linear meets revista impresa), modo oscuro, paleta de comandos y trabajo offline.

**Demo**: abre `index.html` directamente en el navegador o despliega en GitHub Pages / Vercel sin build.

---

## Qué hay de nuevo

### Diseño
- Tipografía editorial: **Instrument Serif** (display), **Manrope** (UI), **JetBrains Mono** (horas).
- Paleta refinada: tinta profunda + crema cálida en claro; carbón + crema en oscuro.
- Sistema de tokens CSS con variables semánticas — fácil de reajustar.
- Textura de grano sutil, transiciones suaves, micro-interacciones.

### Vistas
- **Dashboard** — saludo dinámico, reloj mundial en vivo, métricas (reuniones del mes, próximas 7 días, distribución por confort, top países), próximas reuniones y acciones rápidas.
- **Reuniones** — agrupadas por semana, con filtros por país, estado y búsqueda. Hover revela acciones (estado, ICS, duplicar, editar, eliminar).
- **Calendario** — vista de mes con chips coloreados por nivel de confort. Click en día → nueva reunión prellenada.
- **Clientes** — tarjetas con hora local en vivo, conteo de reuniones y autocompletado de país.

### Productividad
- **⌘K** paleta de comandos (navegar, crear, exportar, alternar tema).
- **Atajos de teclado** — `N` nueva reunión, `C` nuevo cliente, `T` hoy, `G+D/M/C/L` navegar, `?` ayuda, `Esc` cerrar.
- **Toasts** y diálogos de confirmación (no más `alert`/`confirm` del navegador).
- **Importar / exportar JSON** — backup completo de tus datos.
- **Exportar ICS** — reunión individual, semana o todo.

### Datos
- **Estado** (pendiente / hecha / cancelada) y **prioridad** (alta / media / baja) por reunión.
- **Migración automática** desde la versión anterior (`reuniones`, `clientes` → `mr.meetings.v2`, `mr.clients.v2`).
- 42 países con bandera, capital y zona horaria.

### Tema
- Claro / oscuro con persistencia. Botón en la barra lateral.

---

## Estructura

```
build/
└── index.html    # Todo en un solo archivo: HTML + CSS + JS vanilla
```

Sin build, sin dependencias npm. Solo fuentes Google y un par de utilidades nativas.

---

## Despliegue

**GitHub Pages**: copia `build/index.html` a la raíz del repositorio (o a `/docs`).
**Vercel / Netlify**: arrastra la carpeta `build/`.
**Local**: doble click en `index.html`.

---

## Atajos

| Tecla | Acción |
|---|---|
| `⌘K` / `Ctrl+K` | Abrir paleta de comandos |
| `N` | Nueva reunión |
| `C` | Nuevo cliente |
| `T` | Saltar a hoy |
| `G` luego `D` | Ir a Dashboard |
| `G` luego `M` | Ir a Reuniones |
| `G` luego `C` | Ir a Calendario |
| `G` luego `L` | Ir a Clientes |
| `?` | Ver atajos |
| `Esc` | Cerrar modal |
| `⌘+Enter` | Guardar (en modal) |

---

## Notas técnicas

- **Conversión horaria**: `Intl.DateTimeFormat` con `timeZone` real, sin libs.
- **Confort**: hora ideal (9–18h España), incómoda (7–9h o 18–21h), fuera de horario (resto).
- **ICS**: formato VCALENDAR estándar, compatible con Google Calendar, Outlook, Apple Calendar.
- **Persistencia**: `localStorage` con migración perezosa al cargar.
