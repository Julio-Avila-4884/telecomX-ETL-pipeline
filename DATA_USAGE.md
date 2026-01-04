# Datos de ejemplo y uso

Este repositorio incluye archivos de ejemplo para probar el pipeline ETL de telecomunicaciones.

Archivos incluidos (rutas relativas al root del repo):

- `data/source/Sample_TelecomX_Data.json` — archivo de entrada (formato fuente/original).
- `data/raw/Sample_telecomX_raw.json` — archivo intermedio generado por la etapa de ingestión.
- `data/Final/Sample_telecom_final.csv` — archivo de salida final con los datos transformados.

Notas:

- El pipeline por defecto carga las rutas relativas definidas en `src/main.py`:

  - entrada: `data/source/Sample_TelecomX_Data.json`
  - raw: `data/raw/Sample_telecomX_raw.json`
  - salida: `data/final/Sample_telecom_final.csv` (ver nota sobre mayúsculas)

- En sistemas con distinción entre mayúsculas y minúsculas ajuste las carpetas si es necesario: en este repositorio la carpeta de salida es `data/Final` (F mayúscula); `src/main.py` referencia `data/final` en minúsculas — en Windows esto no suele afectar, pero en Linux/macOS sí.

Cómo probar con los datos de ejemplo:

1. Asegúrese de tener las dependencias instaladas (recomendado crear virtualenv):

```bash
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

2. Ejecutar el pipeline completo (usará los archivos de ejemplo incluidos):

```bash
python src/main.py
```

3. Verifique los archivos generados en `data/raw` y `data/Final`.

Ejecutar etapas individualmente:

- Puede importar y llamar `ingest.ingest_json`, `transform.transform_data` y `load.load_to_csv` desde un REPL o un script de prueba apuntando a las rutas de ejemplo.

Si desea que integre este contenido directamente en `README.md`, dígamelo y lo hago (actualizaré las rutas y tomaré en cuenta la mayúscula/minúscula).