
## Strapi <img align="left" alt="Strapi" width="30px" style="padding-right:0px;" src="https://assets.super.so/e7c0f16c-8bd3-4c76-8075-4c86f986e1b2/uploads/favicon/9c68ae10-0a8a-4e3f-9084-3625b19df9cb.png" />

- **Node**: Versión **v20.10.0** (REQUIRED)
1. **Crear el proyecto**:
   ```bash
   npx create-strapi-app my-server --quickstart
   ```
   
   Al ejecutar el comando anterior, responde a las preguntas de la siguiente manera:
   
   - `Please log in or sign up.` → **Skip**
   - `Do you want to use the default database (sqlite)?` → **Yes**
   - `Start with an example structure & data?` → **No**
   - `Start with Typescript?` → **Yes**
   - `Install dependencies with npm?` → **Yes**
   - `Initialize a git repository?` → **No**

2. **Crear una nueva colección**:
   - Navega a **Content-Type Builder > Create new collection type**.
   - Desactiva la opción **"Draft & publish"** en **Advanced Settings** para evitar problemas de visualización.
   - Ingresa el nombre de la colección en singular (campo “display name”) y selecciona **Continue**.

   **Nota**: En VPS, Strapi puede no reiniciarse automáticamente al crear colecciones. Monitorea el log para verificar la creación de la colección y actualiza la página manualmente si ves el mensaje **"Waiting for restart..."**. Esto puede requerir varios "refresh" hasta que se elimine el loader.

3. **Ingresar información en la colección**:
   - Dirígete a **Content Manager > "nombre-de-la-coleccion" > Create new entry** para agregar datos.

4. **Asignar permisos a la colección**:
   - Ve a **Settings > USERS & PERMISSIONS PLUGIN > Roles > Public > Permissions** y habilita los permisos para **"nombre-de-la-coleccion"** según corresponda.

5. **Acceso a la API**:
   - Una vez configurada la colección, puedes acceder a su API mediante la URL:
     ```
     http://localhost:1337/api/nombre-de-la-coleccion-en-plural
     ```

6. **Comandos básicos de Strapi**:
   - Desarrollo:
     ```bash
     npm run develop
     ```
   - Construcción (Build):
     ```bash
     npm run build
     ```
   - Inicio (Producción):
     ```bash
     npm run start
     ```


## Node con NVM <img align="left" alt="Node" width="30px" style="padding-right:0px;" src="https://cdn-icons-png.flaticon.com/512/5968/5968322.png" />
1. **Instalar NVM (Node Version Manager)**:
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
   ```
2. **Instalar una versión específica de Node**:
   ```bash
   nvm install 20.10.0
   ```
3. **Seleccionar versión de Node para el sistema**:
   ```bash
   nvm use 20.10.0
   ```
4. **Establecer la versión como predeterminada**:
   ```bash
   nvm alias default 20.10.0
   ```
5. **Verificar la versión de Node instalada**:
   ```bash
   node -v
   ```


## Configuración de PM2 <img align="left" alt="PM2" width="30px" style="padding-right:0px;" src="https://raw.githubusercontent.com/gilbarbara/logos/main/logos/pm2-icon.svg" />
PM2 es un administrador de procesos de Node.js que permite manejar proyectos en segundo plano.

1. **Instalar PM2 globalmente**:
   ```bash
   npm install pm2 -g
   ```
2. **Ubicarse en el directorio del proyecto** en el que quieres usar PM2.
3. **Compilar el proyecto (Build)**:
   ```bash
   npm run build
   ```
4. **Iniciar el proyecto con PM2**:
   ```bash
   pm2 start npm --name "nombre-del-proyecto" -- start
   ```
5. **Configurar PM2 para iniciar automáticamente al encender el sistema**:
   ```bash
   pm2 startup
   pm2 save
   ```

6. **Comandos útiles de PM2**:
   - Reiniciar un proyecto específico:
     ```bash
     pm2 restart nombre-del-proyecto
     ```
   - Reiniciar todos los proyectos:
     ```bash
     pm2 restart all
     ```
   - Detener un proyecto específico:
     ```bash
     pm2 stop nombre-del-proyecto
     ```
   - Detener todos los proyectos:
     ```bash
     pm2 stop all
     ```
   - Eliminar un proyecto específico de PM2:
     ```bash
     pm2 delete nombre-del-proyecto
     ```
   - Eliminar todos los proyectos:
     ```bash
     pm2 delete all
     ```
   - Listar todos los proyectos en PM2:
     ```bash
     pm2 list
     ```
