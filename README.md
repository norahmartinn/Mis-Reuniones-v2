# Mis Reuniones · v2

Aplicación de un solo archivo para gestionar reuniones internacionales con conversión automática de zona horaria a España. Rediseñada con una estética editorial-SaaS (Linear meets revista impresa), modo oscuro, paleta de comandos y trabajo offline.

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

## Notas técnicas

- **Conversión horaria**: `Intl.DateTimeFormat` con `timeZone` real, sin libs.
- **Confort**: hora ideal (9–18h España), incómoda (7–9h o 18–21h), fuera de horario (resto).
- **ICS**: formato VCALENDAR estándar, compatible con Google Calendar, Outlook, Apple Calendar.
- **Persistencia**: `localStorage` con migración perezosa al cargar.
