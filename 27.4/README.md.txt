# UAT/UPC Causal Attractor – Pipeline de Validación

Este repositorio contiene los scripts utilizados para la detección
del atractor escalar predicho por el marco UAT/UPC en datos públicos
de LIGO-Virgo (GWOSC).

## Archivos

1.  **`pipeline_unificado_rms_svd.py`**  
    Pipeline principal: descarga el catálogo GWTC, analiza 219 eventos
    mediante RMS normalizado (ventanas de 1 s) con deriva inflacionaria
    del atractor, triangula las detecciones por SVD y ejecuta controles
    de ruido. Genera el gráfico Aitoff y el CSV de detecciones.

2.  **`control_fase_aleatoria_8canales.py`**  
    Demuestra que el método anterior de 8 canales virtuales producía
    un Índice Γ artificial (~3.46 incluso tras aleatorizar la fase),
    por lo que fue descartado.

3.  **`verificacion_hash.py`**  
    Compara el hash MD5 de un segmento oficial de GWOSC con el de
    archivos locales previamente utilizados, confirmando una
    discrepancia que motivó el cambio a descarga directa.

## Ejecución

Instalar dependencias: `pip install gwpy astropy pandas matplotlib`

Ejecutar los scripts en cualquier orden. El pipeline principal
descarga datos oficiales y no requiere archivos locales.

## Referencias

- Resonant Hunter v8.4: [10.5281/zenodo.18446712](https://doi.org/10.5281/zenodo.18446712)
- UAT: [10.5281/zenodo.17729221](https://doi.org/10.5281/zenodo.17729221)
- UPC: [10.5281/zenodo.18210808](https://doi.org/10.5281/zenodo.18210808)