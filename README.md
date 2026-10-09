# ESTELYA · Gestión Estética

![ESTELYA](assets/estelya_logo_small.png)

**Software de escritorio para comercios de estética · CORE FREE · v2.0.0-rc.3.2 (candidata)**

**QuintaDimensión Tecnología** presenta ESTELYA, una aplicación administrativa local-first dirigida a centros de estética, peluquerías, spas y servicios personales. El objetivo comercial es ofrecer el núcleo de gestión gratuitamente y comercializar solamente futuras extensiones opcionales.

> **Aviso:** Esta es una presentación técnica del portfolio, no un instalador ni software validado para tratar datos clínicos reales. Las condiciones de uso gratuito y la denominación comercial requieren revisión definitiva antes de distribuir a comercios.

## Pantallas del programa (capturas reales del modo DEMO)

Estas capturas provienen de ESTELYA ejecutada con **datos ficticios** en una interfaz virtual Linux. No son diseños conceptuales ni acreditan compatibilidad final con Windows.

### Dashboard
![Dashboard](screenshots/dashboard.png)

### Agenda
![Agenda](screenshots/agenda.png)

### Clientes
![Clientes](screenshots/clientes.png)

### Ventas y Caja
![Ventas](screenshots/ventas.png)
![Caja](screenshots/caja.png)

### Inventario
![Inventario](screenshots/inventario.png)

### Configuración
![Configuración](screenshots/configuracion.png)

## Áreas de gestión

| Área | Capacidades presentes |
|---|---|
| Inicio | Indicadores del negocio y resumen de agenda |
| Agenda | Turnos y notas administrativas |
| Clientes | Fichas y fotografías |
| Servicios | Tratamientos y consentimientos |
| Comercial | Ventas, caja y promociones |
| Inventario | Productos, existencias y movimientos |
| Administración | Reportes, privacidad y pantallas locales de soporte/extensiones |

## Tecnologías

Python, Tkinter/CustomTkinter, SQLite, Pillow, `cryptography`, Argon2id, ReportLab y python-docx. PyInstaller e Inno Setup son parte de la preparación de distribución Windows.

## Privacidad, alcance y límites

- Opera sobre base SQLite local.
- Modo DEMO efímero aislado de datos reales.
- Cifrado selectivo; no protege automáticamente todos los adjuntos.
- Sin telemetría remota por defecto; no existe backend comercial de gadgets.
- Estado RC: pruebas automatizadas y GUI virtual aprobadas; pruebas Windows del instalador pendientes.
- No se entregan ejecutables ni código completo en este repositorio de portfolio.

## Distribución y derechos

El proyecto se proyecta como **software gratuito de uso** para comercios, con futuras herramientas opcionales de pago. La visibilidad del portfolio no concede licencia de reutilización del código ni convierte al proyecto en open source. Consultar [estado legal y borrador](LICENSE_TERMS_DRAFT.md) y [copyright](COPYRIGHT.md).

## Desarrollo y próximos pasos

Consultar [arquitectura](ARCHITECTURE.md), [privacidad](PRIVACY.md), [roadmap](ROADMAP.md) y [avisos de terceros](THIRD_PARTY_NOTICES.md).

**© 2026 QuintaDimensión Tecnología. Todos los derechos reservados.**
