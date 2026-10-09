# ESTELYA — Verificación técnica pública

**Producto:** ESTELYA · Gestión Estética — CORE FREE  
**Desarrollador:** QuintaDimensión Tecnología  
**Versión evaluada:** `v2.0.0-rc.3.2` — versión candidata, no estable  
**Fecha del informe:** 2026-10-09

## Alcance de esta edición

Este repositorio muestra el portfolio de ESTELYA mediante documentación y capturas reales de la aplicación en modo demostración, con datos ficticios. **No contiene el código fuente propietario completo, un instalador Windows ni una versión comercial lista para producción.**

## Evidencia de validación disponible

| Comprobación | Resultado registrado | Alcance y límite |
|---|---|---|
| Compilación sintáctica Python (`compileall`) | Aprobada | No garantiza ausencia de errores en ejecución |
| Pruebas automatizadas (`pytest`) | 22 aprobadas | Cobertura parcial de los flujos del sistema |
| Prueba gráfica virtual | 17 de 17 pantallas abiertas | Entorno Linux virtual (Xvfb), no Windows físico |
| Prueba de cierre de demostración | Aprobada en entorno virtual | Pendiente reconfirmar comportamiento en Windows |
| Capturas de pantalla | 7 PNG reales con datos ficticios | Demuestran presentación visual, no certifican la funcionalidad comercial |
| Instalación PyInstaller/Inno Setup Windows | **No probada** | No se ofrece EXE ni instalador público |
| Análisis Ruff y `pip-audit` | **No ejecutados** | Auditorías de estilo y dependencias pendientes |
| Auditoría legal de marca y condiciones de uso | **Pendiente** | El documento de licencia actual es sólo un borrador |

## Protección y privacidad: alcance real

ESTELYA utiliza almacenamiento local SQLite y dispone de cifrado selectivo. No se considera cifrada toda la base de datos ni todos los archivos adjuntos. El modo demostración utiliza datos ficticios y no requiere telemetría remota. No hay backend comercial operativo de extensiones ni de soporte remoto.

**No introducir datos clínicos reales en esta versión candidata.**

## Próximas validaciones antes de distribuir a comercios

1. Instalación, arranque y cierre en Windows 11 x64.
2. Pruebas de recuperación, backup y migración con copias ficticias.
3. Pruebas de operaciones completas de ventas, caja, stock y consentimientos.
4. Revisión de privacidad, datos sensibles y licencias de terceros.
5. Definir condiciones legales y comprobar la disponibilidad comercial de la marca.

El código completo se mantiene fuera de la Portfolio Edition pública.
