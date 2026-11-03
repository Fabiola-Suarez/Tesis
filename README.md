# Análisis comparativo de los tiempos de ejecución en motores de bases de datos relacionales

**Motores estudiados:** PostgreSQL y MariaDB.
**Reuniones con dirección:** cada 15 días.  
**Infraestructura:** Docker, WSL2.

## Resumen

El trabajo compara los tiempos de ejecución de operaciones SQL equivalentes en PostgreSQL y MariaDB, utilizando esquemas y datasets comunes, distintos volúmenes de datos y escenarios con y sin índices. Se prevé repetir las mediciones, estudiar las posibles causas de las diferencias de rendimiento y evaluar optimizaciones dentro de escenarios definidos. El trabajo **no** busca determinar un motor superior en todos los contextos.

## Objetivo general

Comparar los tiempos de ejecución de operaciones SQL equivalentes en los motores de bases de datos relacionales PostgreSQL y MariaDB, mediante pruebas realizadas sobre conjuntos de datos comunes y bajo condiciones controladas, con el propósito de analizar las diferencias de rendimiento, identificar posibles factores que las originan y evaluar alternativas de optimización.

## Documentación principal

- [Capítulo 1 — Introducción](docs/tesina/01-introduccion.md)
- [Anexo I original](docs/propuesta/anexo-I-original.docx)
- [Bibliografía inicial](docs/propuesta/bibliografia.md)
- [Cronograma](docs/propuesta/cronograma.md)

## Organización

| Carpeta | Finalidad |
|---|---|
| `docs/propuesta/` | Anexo, bibliografía, cronograma y requisitos. |
| `docs/tesina/` | Capítulos académicos. |
| `docs/entorno/` | Hardware y alternativas de infraestructura. |
| `docs/gestion/` | Estado del proyecto, decisiones, riesgos y seguimiento. |
| `docs/reuniones/` | Agenda de reuniones con director. |
