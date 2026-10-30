# Pruebas unitarias — Caso A: Swag Labs

## Alcance

Este proyecto demuestra pruebas unitarias con `pytest` para dos casos de uso distintos de CU-01:

- **CU-03 — Capturar datos de envío (RN-A5):** nombre, apellido y código postal obligatorios; los valores vacíos o con solo espacios se consideran vacíos; se devuelve el primer error según el orden indicado en la ficha.
- **CU-04 — Calcular el resumen del pedido (RN-A6):** impuesto del 8 %, redondeo al centavo con mitad hacia arriba, total igual al subtotal más el impuesto y rechazo de subtotales negativos.

## Nota sobre el código fuente

El PDF facilitado contiene las reglas y las firmas esperadas de las funciones, pero no contiene el ZIP con los módulos originales. Por ello, `src/checkout.py` es una **implementación de apoyo creada para esta práctica a partir de la ficha del PDF**. No se presenta como código original del profesor. Si posteriormente se consigue el código oficial, las pruebas deberán ejecutarse contra ese módulo y cualquier diferencia con la ficha se documentará como hallazgo, sin modificar las pruebas para ocultarla.

## Requisitos

- Python 3.10 o superior
- Visual Studio Code (opcional, recomendado)
- Git (para publicar la entrega)

## Ejecutar en Windows

Abre esta carpeta en Visual Studio Code. En la terminal integrada, ejecuta:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m pytest -v
```

Si PowerShell impide activar el entorno, puedes ejecutar pytest directamente con:

```powershell
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe -m pytest -v
```

## Ejecutar en macOS o Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m pytest -v
```

## Resultado esperado

Con la implementación de apoyo incluida, deben pasar **17 pruebas/casos parametrizados** (pytest puede mostrar el número exacto según cómo contabilice los casos parametrizados). Para ejecutar de nuevo, basta con activar el entorno y correr `python -m pytest -v`.

## Estructura

```text
Pruebas unitarias/
├── README.md
├── requirements.txt
├── pytest.ini
├── src/
│   ├── __init__.py
│   └── checkout.py
├── tests/
│   └── test_checkout.py
├── docs/
│   ├── DOCUMENTACION.md
│   └── GUION_VIDEO.md
└── .vscode/
    └── settings.json
```

## Publicar en GitHub

1. Crea un repositorio nuevo en GitHub, por ejemplo `pruebas-unitarias-swaglabs`.
2. Abre esta carpeta en VS Code y ejecuta:

```bash
git init
git add .
git commit -m "Implementa pruebas unitarias CU-03 y CU-04"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/pruebas-unitarias-swaglabs.git
git push -u origin main
```

3. Sustituye `TU-USUARIO` por tu nombre de usuario real y copia el enlace del repositorio para la entrega. No uses una URL inventada: copia la que GitHub muestre en tu cuenta.

## Uso de IA

Se utilizó IA generativa como apoyo para organizar las pruebas y redactar la documentación. Los casos y resultados esperados se derivaron de las reglas RN-A5 y RN-A6 del PDF facilitado; el código de apoyo y las pruebas se ejecutaron localmente con pytest.
