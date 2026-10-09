# Arquitectura de ESTELYA

Monolito modular de escritorio basado en Python 3, Tkinter/CustomTkinter y SQLite.

```text
launcher.py (selector comercio / demo)
  -> app.py (seguridad e inicialización)
     -> seguridad.py (claves y recuperación)
     -> database.py / services.py
     -> ui.py -> pages_dashboard/operations/finance/clinical/marketing/business
     -> backup.py (SQLite backup() + contenedor cifrado)
     -> telemetry.py (diagnósticos locales)
```

Las siete áreas visibles agrupan 17 pantallas. Los datos reales viven en una carpeta diferente del directorio fuente. La demo crea una base temporal que se elimina tras liberar los manejadores de logs y SQLite.

**Limitaciones:** parte del código UI aún consulta SQL directamente; `services.py` contiene responsabilidades grandes. No hay RBAC multiusuario completo, servidor remoto de soporte, aislamiento de extensiones ni cifrado general de adjuntos. No llamar a la aplicación producto de seguridad certificado.

La evolución recomendada es extraer servicios y repositorios sin reescribir la interfaz completa y probar migraciones mediante copias de bases ficticias.
