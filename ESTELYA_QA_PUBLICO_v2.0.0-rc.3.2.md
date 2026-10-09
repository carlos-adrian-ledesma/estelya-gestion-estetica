# ESTELYA — Verificación técnica pública

**Producto:** ESTELYA · Gestión Estética — CORE FREE  
**Desarrollador:** QuintaDimensión Tecnología  
**Versión evaluada:** `v2.0.0-rc.3.2` — Release Candidate  
**Fecha del informe:** 2026-10-09  
**Estado:** Portfolio publicado · Windows DEMO disponible · Validación comercial pendiente

---

## 1. Alcance de esta edición

ESTELYA es una aplicación de escritorio para la gestión administrativa de centros de estética, peluquerías, spas y comercios de belleza.

Este repositorio público presenta el proyecto mediante documentación técnica, capturas auténticas del modo demostración y una versión ejecutable para Windows x64.

La aplicación está desarrollada principalmente con Python, CustomTkinter y SQLite.

El proyecto utiliza un modelo **CORE FREE**, orientado a ofrecer gratuitamente las herramientas administrativas principales y desarrollar futuras extensiones comerciales opcionales.

### Distribución actual

- Portfolio Edition pública.
- DEMO compilada para Windows x64.
- Ejecución con datos ficticios y temporales.
- Sin necesidad de instalar Python para utilizar el paquete compilado.
- Sin conexión obligatoria a Internet.
- Código fuente completo reservado para desarrollo privado.

**Importante:** esta versión continúa en evaluación. No constituye una edición comercial certificada para gestionar datos reales de clientes o pacientes.

---

## 2. Evidencia de validación técnica

| Comprobación | Resultado registrado | Alcance y límite |
|---|---|---|
| Compilación sintáctica Python (`compileall`) | Aprobada | No garantiza ausencia de errores en ejecución |
| Pruebas automatizadas del proyecto base | 22 aprobadas | Cobertura parcial de los flujos administrativos |
| Pruebas automatizadas del kit DEMO | 27 aprobadas | Incluyen controles del modo demostración y distribución |
| Prueba gráfica virtual | 17 de 17 pantallas abiertas | Entorno Linux virtual, no Windows físico |
| Cierre de demostración | Aprobado en entorno virtual | Pendiente confirmación funcional completa en Windows |
| Capturas de pantalla | 7 PNG auténticos | Datos ficticios; no certifican funcionalidad comercial |
| Compilación Windows x64 | Ejecutable generado | Compilación mediante PyInstaller en Windows |
| Empaquetado de distribución | ZIP generado | Paquete destinado a GitHub Releases |
| Publicación de la DEMO | Completada | Disponible como Pre-release |
| Archivo SHA-256 | Publicado | GitHub informa una huella SHA-256 del ZIP |
| Pruebas manuales completas en Windows | Pendientes de documentación | Deben verificarse navegación, operaciones y cierre |
| Instalador Inno Setup comercial | No validado | La DEMO se distribuye como ZIP portable |
| Análisis Ruff y `pip-audit` | No ejecutados | Auditorías complementarias pendientes |
| Auditoría legal de marca y condiciones de uso | Pendiente | Las condiciones actuales son provisionales |

Los resultados corresponden a diferentes etapas de desarrollo. Las 22 pruebas del proyecto base y las 27 del kit DEMO no deben interpretarse automáticamente como 49 pruebas independientes.

---

## 3. Descarga pública de ESTELYA DEMO

**Versión:** `v2.0.0-rc.3.2`  
**Sistema objetivo:** Windows x64  
**Modalidad:** Demostración gratuita

[Descargar ESTELYA DEMO para Windows](https://github.com/carlos-adrian-ledesma/estelya-gestion-estetica/releases/download/v2.0.0-rc.3.2/ESTELYA_DEMO_Windows_x64_v2.0.0-rc.3.2.zip)

### Instrucciones

1. Descargar el archivo ZIP.
2. Extraer completamente su contenido.
3. Abrir la carpeta `ESTELYA_DEMO`.
4. Ejecutar `ESTELYA_DEMO.exe`.
5. Explorar los módulos utilizando información ficticia.
6. Cerrar normalmente el programa.

La DEMO no debe utilizarse para operaciones comerciales reales.

---

## 4. Integridad del paquete Windows

**Archivo:** `ESTELYA_DEMO_Windows_x64_v2.0.0-rc.3.2.zip`

**Tamaño:** 34.848.377 bytes

**SHA-256 informado por GitHub:**

`4a44ee807db4d696d01e0f67fdcee8ed712c1b28f8e4caae4a99174576c237c6`

[Descargar archivo de verificación SHA-256](https://github.com/carlos-adrian-ledesma/estelya-gestion-estetica/releases/download/v2.0.0-rc.3.2/ESTELYA_DEMO_Windows_x64_v2.0.0-rc.3.2.zip.sha256.txt)

Para verificar localmente el ZIP:

```cmd
certutil -hashfile "ESTELYA_DEMO_Windows_x64_v2.0.0-rc.3.2.zip" SHA256
```

El resultado debe coincidir con la huella registrada por GitHub.

La comprobación criptográfica de un archivo permite detectar alteraciones respecto del archivo de referencia. No garantiza por sí sola ausencia de vulnerabilidades, malware o errores funcionales.

---

## 5. Protección y privacidad

ESTELYA utiliza una arquitectura local-first basada en SQLite.

### Características existentes

- Almacenamiento administrativo local.
- Modo demostración con datos ficticios.
- Entorno temporal aislado.
- Cifrado selectivo de determinados campos.
- Mecanismos locales de respaldo y recuperación.
- Telemetría externa no habilitada por defecto.
- Funcionamiento administrativo sin conexión obligatoria a Internet.

### Limitaciones actuales

El cifrado selectivo no implica que toda la base de datos y sus archivos adjuntos estén cifrados.

El programa todavía requiere validaciones adicionales de seguridad, migración, recuperación y protección de información sensible.

No existe actualmente un backend comercial operativo de soporte remoto, licenciamiento de extensiones ni recepción de telemetría.

**No introducir datos clínicos reales ni información personal sensible en esta versión candidata.**

---

## 6. Módulos presentados

| Área | Funcionalidades |
|---|---|
| Inicio | Dashboard e indicadores administrativos |
| Agenda | Turnos, calendario y notas |
| Clientes | Fichas administrativas y fotografías |
| Servicios | Tratamientos y consentimientos |
| Comercial | Ventas, caja y promociones |
| Inventario | Productos y stock |
| Administración | Reportes, configuración, privacidad y herramientas informativas |

La presencia de estos módulos en la demostración no implica certificación de todos los procesos empresariales.

---

## 7. Próximas validaciones

Antes de considerar ESTELYA apta para una distribución comercial estable, será necesario:

1. Documentar el inicio, navegación y cierre real en Windows 11 x64.
2. Comprobar ausencia de errores al eliminar archivos temporales del modo DEMO.
3. Probar operaciones completas de ventas, caja, inventario y agenda.
4. Validar backups, restauración y migración utilizando bases ficticias.
5. Medir rendimiento en computadoras de oficina con 8 GB de RAM y SSD.
6. Revisar licencias y vulnerabilidades de dependencias.
7. Validar el instalador comercial definitivo.
8. Revisar condiciones legales de distribución y disponibilidad de la marca.
9. Verificar la protección de información personal y clínica.
10. Completar documentación y controles de calidad de futuras versiones.

---

## 8. Clasificación técnica actual

**Portfolio:** Publicado.

**DEM O Windows:** Compilada, empaquetada y disponible públicamente como versión candidata.

**Validación funcional completa en Windows:** Pendiente de confirmación documentada.

**Distribución comercial estable:** No aprobada todavía.

**Full Source:** Desarrollo privado.

---

## 9. Derechos y desarrollo

ESTELYA es desarrollado por **QuintaDimensión Tecnología**.

El programa principal se proyecta como software gratuito para comercios, con extensiones y servicios tecnológicos opcionales.

La disponibilidad gratuita del ejecutable no implica que el código fuente sea open source ni autoriza automáticamente su modificación o redistribución.

Las condiciones finales de utilización y distribución requieren revisión legal.

**© 2026 QuintaDimensión Tecnología. Todos los derechos reservados.**
