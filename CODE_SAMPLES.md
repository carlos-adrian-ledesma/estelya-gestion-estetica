# ESTELYA — Selected Code Samples (Portfolio Edition)

**Project:** ESTELYA · Gestión Estética  
**Version:** v2.0.0-rc.3.2 (Release Candidate)  
**Developer:** QuintaDimensión Tecnología  
**Language:** Python 3  
**Scope:** Carefully selected excerpts from the private DEMO Build Kit. This file is for technical portfolio review, not a complete or runnable source distribution.

## 1. Modular navigation without GUI coupling

The original project separates the menu's seven business areas from the visual widgets. This lets navigation routing be checked without starting Tkinter/CustomTkinter.

**Source:** `navigation.py` (excerpt from the private v2.0.0-rc.3.2 DEMO Build Kit)

```python
"""Navegación agrupada: menos botones, sin quitar pantallas existentes.

No importar Tkinter aquí: este mapa se prueba sin una interfaz gráfica.
"""
from __future__ import annotations

NAV_GROUPS = {
    'Inicio': ('Dashboard',),
    'Agenda': ('Agenda', 'Notas'),
    'Clientes': ('Clientes', 'Fotos'),
    'Servicios': ('Tratamientos', 'Consentimientos'),
    'Comercial': ('Ventas', 'Caja', 'Promociones'),
    'Inventario': ('Productos', 'Stock'),
    'Administración': ('Configuración', 'Privacidad', 'Reportes', 'Soporte', 'Extensiones'),
}

PAGE_TO_GROUP = {page: section for section, pages in NAV_GROUPS.items() for page in pages}


def group_of(page: str) -> str:
    """Un nombre de pantalla individual siempre conserva su ruta."""
    return PAGE_TO_GROUP[page]


def first_page(section: str) -> str:
    return NAV_GROUPS[section][0]
```

## 2. Regression test for screen coverage

This test checks that the grouped sidebar still exposes all 17 original screens and retains specific page-to-area mappings. The assertions are from the actual project test suite, not a conceptual example.

**Source:** `tests/test_navigation_shutdown.py` (selected test function)

```python
def test_grouped_navigation_preserves_all_pages():
    original={
        'Dashboard','Agenda','Clientes','Tratamientos','Caja','Ventas',
        'Productos','Stock','Fotos','Consentimientos','Promociones','Reportes',
        'Notas','Extensiones','Soporte','Privacidad','Configuración'
    }
    assert len(NAV_GROUPS)==7
    assert set(PAGE_TO_GROUP)==original
    assert sum(len(v) for v in NAV_GROUPS.values())==len(original)
    assert group_of('Notas')=='Agenda'
    assert group_of('Promociones')=='Comercial'
    assert group_of('Consentimientos')=='Servicios'
    assert group_of('Reportes')=='Administración'
    assert group_of('Privacidad')=='Administración'
    assert group_of('Fotos')=='Clientes'
    assert first_page('Agenda')=='Agenda'
```

## 3. Synthetic demo records inside a database transaction

The DEMO seed creates sample clients, one professional, and an inventory product inside a database transaction. It checks for existing demo clients before inserting. This excerpt contains no real client data or application credentials.

**Source:** `demo_seed.py` (from the private v2.0.0-rc.3.2 DEMO Build Kit)

```python
"""Demostración autocontenida sin datos de comercios ni contraseñas públicas."""
from __future__ import annotations

from utilidades import argentina_now


def seed_demo(db):
    if db.conn.execute('SELECT COUNT(*) FROM clients').fetchone()[0]:
        return
    ts = argentina_now().isoformat(timespec='seconds')
    with db.tx() as conn:
        for number in range(1, 5):
            conn.execute(
                '''INSERT INTO clients(first_name,last_name,phone,email,notes,created_at)
                   VALUES(?,?,?,?,?,?)''',
                (f'Ejemplo {number:02}', 'DEMO', '', '',
                 db.security.encrypt('Registro ficticio de demostración'), ts),
            )
        conn.execute(
            "INSERT INTO professionals(name,specialty,active) VALUES('Profesional DEMO','Estética',1)"
        )
        conn.execute(
            '''INSERT INTO products(name,category,code,cost,price,stock,min_stock)
               VALUES('Producto de muestra DEMO','Demostración','DEMO-01',1000,2200,12,3)'''
        )
```

## Engineering notes and limits

- The public repository remains the **Portfolio Edition**; full application source, authentication internals and sensitive implementation details remain private. Selected branding and screenshots are already public portfolio assets.
- The code excerpts illustrate real design choices; they are **not standalone modules** and require additional private components in the full application.
- Tests in the Build Kit and the public QA documentation address only their declared scope. These excerpts alone do not certify the security of the product or its readiness for production.
- The Windows evaluation DEMO is published separately under GitHub Releases.

**Portfolio:** [README.md](README.md)  
**Architecture:** [ARCHITECTURE.md](ARCHITECTURE.md)  
**QA:** [ESTELYA_QA_PUBLICO_v2.0.0-rc.3.2.md](ESTELYA_QA_PUBLICO_v2.0.0-rc.3.2.md)

---

© 2026 QuintaDimensión Tecnología. All rights reserved. These selected excerpts are provided for portfolio review. Their publication does not grant an open-source license or permission to redistribute the complete software.
