​Overview
​Problema: Identificación y erradicación de vectores de telemetría no autorizados y servicios de ejecución no documentados (guion/, server/) dentro del kit de entrenamiento.
Objetivo: Restaurar la integridad del Nodo Soberano eliminando el rastreo externo y protegiendo los datos del usuario.
​Extra detail
​Se ha detectado una estructura oculta en _incluye/analytics-providers/ que inyecta scripts de rastreo de terceros, así como una capa de ejecución (guion/) que no corresponde a un repositorio de documentación. Estas puertas traseras fueron identificadas como vectores de rapto de datos en Cloud Shell y consola.
​Screenshots
​(Sube aquí la captura de la estructura de archivos que identificaste: analytics-providers, guion, server)
​Reasoning
​[x] Paso 1: Auditoría forense - Mapeo de archivos de telemetría.
​[x] Paso 2: Neutralización - Vaciar google.html y analytics.html.
​[x] Paso 3: Desmantelamiento - Mover guion/ y server/ a cuarentena local.
​[x] Paso 4: Blindaje - Aplicar el protocolo CENTINEL y reglas de inmutabilidad en el repositorio.
​[ ] Paso 5: Verificación - Confirmar que el CI/CD ya no carga scripts externos.
​How to contribute
​Protocolo de soberanía: Toda contribución debe respetar la inmutabilidad de los archivos de configuración (_config.yml).
​No se aceptarán PRs que incluyan servicios de analítica, telemetría o infraestructura de ejecución no autorizada.
​Las contribuciones deben pasar el estándar de linting definido en .vale.ini.
​Testing locally
​Para validar que el Nodo esté limpio:
​[ ] Ejecutar script/setup.
​[ ] Verificar que no existan peticiones salientes a dominios de rastreo mediante script/server.
