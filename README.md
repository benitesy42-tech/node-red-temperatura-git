# Proyecto Node-RED: temperatura simulada y GitHub

Propietario: **benitesy42-tech**.

Proyecto academico para demostrar configuracion de Node-RED Projects, autenticacion SSH y control de versiones con GitHub.

## Funcionamiento

El flujo usa solamente nodos incluidos en Node-RED:

1. **Inject** introduce una temperatura simulada o una entrada no valida.
2. **Function** valida el dato y lo compara con el umbral de 30 grados Celsius.
3. Tres nodos **Debug** muestran el resultado normal, la alarma o el error.

| Entrada | Resultado esperado |
| --- | --- |
| 25, numero | NORMAL |
| 35, numero | ALARMA |
| 30, numero | ALARMA, porque la comparacion es mayor o igual |
| sin-dato, texto | ERROR |

## Archivos

- `flows.json`: flujo editable y ejecutable en Node-RED.
- `package.json`: metadatos y archivos del proyecto; no requiere nodos adicionales.
- `.gitignore`: exclusiones del control de versiones.
- `README.md`: descripcion y comprobacion de sincronizacion.

## Abrir como proyecto

1. Tener Node.js, Node-RED y Git instalados.
2. En el archivo `settings.js` del directorio de usuario de Node-RED, habilitar `editorTheme.projects.enabled: true` y el workflow manual.
3. Reiniciar Node-RED.
4. Configurar la identidad de los commits en **Settings > Git config**.
5. Crear una clave en **SSH Keys > add key** y registrar su clave publica en **GitHub > Settings > SSH and GPG keys**.
6. En **Projects > New > Clone Repository**, usar la URL SSH del repositorio.
7. Abrir el flujo, pulsar **Deploy** y ejecutar las entradas de prueba.

## Flujo de trabajo de Git

1. Al iniciar una nueva sesion de trabajo, hacer **pull** si la rama remota ya existe.
2. Editar el flujo y pulsar **Deploy**.
3. En **History**, pasar los archivos de **Local files** a **Changes to commit** mediante `+ all`.
4. Hacer **commit** con un mensaje descriptivo.
5. En **Commit History > Manage remote branch**, hacer **push** a `origin/main`.
6. Verificar el commit en GitHub.
7. Para probar **pull**, editar esta nota desde GitHub, guardar el commit remoto y traerlo desde Node-RED.

**Deploy** ejecuta el flujo; **commit** registra una version local; **push** envia commits; **pull** incorpora commits remotos.

## Nota para demostrar pull

Estado de sincronizacion: Cambio remoto para demostrar pull 2026-11-12T16-57-23.
