# Automatización de Pruebas en una API de Inmobiliaria

Ejercicio con GitHub Actions para bootcamp de Devops

## Descripción del Proyecto :scroll:

Caso planteado: 
Vas a construir una API REST básica que simula un sistema inmobiliario. Esta API tendrá una ruta que devuelve una lista de inmuebles. Automatizarás su validación usando GitHub Actions con matrices de Node.js, caché de dependencias, y condiciones de ejecución.

- Crear una API simple en Node.js con Express.
- Escribir pruebas automatizadas con Jest.
- Crear un workflow avanzado en GitHub Actions para validar la API.
- Ejecutar en múltiples versiones de Node.js.
- Optimizar tiempos con cacheo y ejecutar tareas condicionales.


## Sobre el proyecto 🚀

👌 1. Inicialización de proyecto

- mkdir realestate-api && cd realestate-api
- npm init -y
- npm install express
- npm install --save-dev jest supertest

- Crea el repositorio realestate-api
- Sube el código a GitHub
- Crea .github/workflows/api-ci.yml
- Copia el workflow avanzado del archivo
- Haz el push
- Ve a Actions en GitHub
- Verifica la ejecución
- Observa el uso del caché y los mensajes condicionales


## Reflexiones

📦 ¿Por qué probar en múltiples entornos de Node.js?
Probar en varias versiones (como 16.x, 18.x, 20.x) permite garantizar que tu API:
- Sea compatible con distintas versiones del entorno en producción: no todos los servidores actualizan Node.js al mismo ritmo.
- Anticipe errores por funciones nuevas o ausentes (como availableParallelism, que viste).
- Evite efectos colaterales al actualizar Node en el futuro, manteniéndolo estable en versiones anteriores.
En resumen, te da confianza de que tu código se comporta bien más allá de tu máquina local 💪

🧪 ¿Por qué validar la salida de una API desde un workflow?
Porque el workflow en CI actúa como tu “portero digital”:
- Verifica que las rutas devuelvan los datos esperados, con los formatos correctos (JSON, status code, etc.).
- Detecta errores introducidos en pull requests, antes de fusionarlos.
- Ayuda a mantener una API estable y confiable, lo que es vital si otros servicios dependen de ella.
Esto convierte tus tests en una barrera de seguridad que protege la experiencia de tus usuarios (y tu tranquilidad).

🚀 ¿Qué pasos agregar para un despliegue a producción?
Si quisieras automatizar el paso a producción luego de validar los tests, podrías sumar:
- Build o empaquetado (si aplica).
- Validación de seguridad estática con herramientas como npm audit, Trivy, etc.
- Despliegue automático a servicios como Render, Vercel, Railway o un servidor con SSH.
- Notificación a Slack, Discord o email al desplegar exitosamente.
- Rollback o versiones anteriores ante fallos (si el entorno lo permite).
Todo eso orquestado desde GitHub Actions o combinado con otros servicios como GitHub Deployments o webhooks.

⛔ Limitaciones de GitHub Actions y cómo enfrentarlas

Limitación -> Posible Solución

- Tiempos de ejecución limitados (6 horas máx por job) -> Divide procesos largos en jobs o usa workflows programados
- Espacio de almacenamiento limitado para artefactos -> Usar actions/upload-artifact solo cuando sea necesario y eliminar artefactos antiguos
- Acceso restringido a secretos en forks o PRs externos -> Usar entornos (environments) y proteger secretos sensibles
- No puedes probar recursos internos de redes privadas directamente -> Utilizar túneles (ngrok, serveo) o runners auto-hosteados dentro de la red
- Costos si excedes límites en cuentas privadas o GitHub Free -> Optimizar el uso, correr tests solo en ramas críticas, o migrar parte del CI a runners locales



## Visuales :mage_woman:

![Captura de pantalla 2025-06-19 210417](https://github.com/user-attachments/assets/3e9f834d-63be-494c-817f-6449a6fd4069)

![Captura de pantalla 2025-06-19 211239](https://github.com/user-attachments/assets/783fc005-f255-4ca0-9970-7416d4b1c602)

![Captura de pantalla 2025-06-19 211311](https://github.com/user-attachments/assets/87af014e-ab63-4f3b-bf2d-10c2cba7d66b)





## Autora ⚡ 

- **Andrea Rosero** ⚡  - [Andrea Rosero](https://github.com/andreaendigital)
