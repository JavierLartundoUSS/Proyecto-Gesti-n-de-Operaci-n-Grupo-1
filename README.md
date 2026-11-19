# Gestión de Operaciones — Grupo 1

## Pronóstico de demanda de filtros automotrices

### Resumen ejecutivo

El Sprint 1 tuvo como objetivo construir un pronóstico mensual de demanda para AutoPartes Sur utilizando la serie histórica de enero de 2020 a diciembre de 2024. La base contiene 60 observaciones mensuales completas, sin valores faltantes, fechas duplicadas, demandas no positivas ni meses ausentes.

La validación respetó el orden temporal: los modelos se entrenaron con los datos de enero de 2020 a diciembre de 2023 y se evaluaron sobre enero a diciembre de 2024. Se compararon una línea base Naive estacional, Holt-Winters aditivo, Random Forest y modelos SARIMA identificados mediante el procedimiento Box-Jenkins.

El modelo seleccionado fue **SARIMA (2,0,2)(0,1,1)₁₂**, priorizado entre los candidatos cuyos residuos superaron las pruebas de Ljung-Box en los rezagos 6 y 12. En la validación de 2024 obtuvo los siguientes resultados:

| Indicador | Resultado |
|---|---:|
| MAE | 438,57 filtros |
| RMSE | 502,41 filtros |
| MAPE | 4,63% |
| Sesgo (real − pronóstico) | −92,80 filtros |
| Pronóstico total para 2025 | 115.529 filtros |

La selección de SARIMA se fundamentó en su menor MAE y RMSE, un MAPE competitivo, bajo sesgo absoluto y residuos sin autocorrelación significativa. El modelo se reentrenó con las 60 observaciones disponibles para generar el pronóstico de enero a diciembre de 2025, acompañado de intervalos de predicción al 95%.

Los resultados obtenidos proporcionan una base cuantitativa para desarrollar la planificación agregada de producción del Sprint 2. 
