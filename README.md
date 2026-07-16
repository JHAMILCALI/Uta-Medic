# Uta Medic

Repositorio con dos proyectos separados:

- `backend`: API creada con NestJS.
- `frontend`: interfaz web creada con React + Vite.

Cada carpeta se inicializa por separado porque cada una tiene su propio
`package.json`, `package-lock.json` y `node_modules`.

## Requisitos

- Node.js instalado.
- npm instalado.
- Dos terminales abiertas para ejecutar backend y frontend al mismo tiempo.

## Inicializacion rapida

Desde la raiz del repositorio:

```bash
cd backend
npm install
npm run start:dev
```

En otra terminal:

```bash
cd frontend
npm install
npm run dev
```

URLs por defecto:

- Backend: `http://localhost:3000`
- Frontend: `http://localhost:5173`

El backend responde `Hello World!` en `GET /`.

## Backend

Carpeta: `backend`

### Instalar dependencias

```bash
cd backend
npm install
```

Si quieres instalar exactamente las versiones del `package-lock.json`, usa:

```bash
npm ci
```

### Ejecutar en desarrollo

```bash
npm run start:dev
```

Este comando ejecuta NestJS en modo watch. Si editas archivos dentro de
`backend/src`, el servidor se reinicia automaticamente.

### Ejecutar en produccion local

```bash
npm run build
npm run start:prod
```

`npm run build` genera la carpeta `backend/dist`.

### Cambiar puerto

Por defecto usa el puerto `3000`. En PowerShell puedes cambiarlo asi:

```powershell
$env:PORT=4000
npm run start:dev
```

### Comandos utiles

```bash
npm run build
npm run start
npm run start:dev
npm run lint
npm run format
npm run test
npm run test:e2e
npm run test:cov
```

### Archivos principales del backend

- `backend/package.json`: define dependencias y scripts del backend.
- `backend/package-lock.json`: fija las versiones instaladas por npm.
- `backend/nest-cli.json`: configuracion de Nest CLI; usa `src` como carpeta fuente.
- `backend/tsconfig.json`: configuracion principal de TypeScript.
- `backend/tsconfig.build.json`: configuracion para compilar el proyecto.
- `backend/eslint.config.mjs`: reglas de lint para revisar codigo TypeScript.
- `backend/.prettierrc`: reglas de formato con Prettier.
- `backend/.gitignore`: archivos y carpetas que Git debe ignorar.
- `backend/src/main.ts`: punto de entrada; crea la app Nest y escucha en `PORT` o `3000`.
- `backend/src/app.module.ts`: modulo principal; conecta controladores y servicios.
- `backend/src/app.controller.ts`: controlador HTTP; define la ruta `GET /`.
- `backend/src/app.service.ts`: servicio con la logica que devuelve `Hello World!`.
- `backend/src/app.controller.spec.ts`: prueba unitaria del controlador.
- `backend/test/app.e2e-spec.ts`: prueba end-to-end del backend.
- `backend/test/jest-e2e.json`: configuracion de Jest para pruebas e2e.
- `backend/dist`: carpeta generada al compilar; no se edita manualmente.
- `backend/node_modules`: dependencias instaladas; no se edita manualmente.

## Frontend

Carpeta: `frontend`

### Instalar dependencias

```bash
cd frontend
npm install
```

Para instalar exactamente desde el lockfile:

```bash
npm ci
```

### Ejecutar en desarrollo

```bash
npm run dev
```

Vite abre el servidor de desarrollo normalmente en `http://localhost:5173`.
Si ese puerto esta ocupado, Vite puede asignar otro y lo mostrara en terminal.

### Compilar para produccion

```bash
npm run build
```

### Previsualizar build

```bash
npm run preview
```

### Comandos utiles

```bash
npm run dev
npm run build
npm run lint
npm run preview
```

### Archivos principales del frontend

- `frontend/package.json`: define dependencias y scripts del frontend.
- `frontend/package-lock.json`: fija las versiones instaladas por npm.
- `frontend/index.html`: HTML base; contiene el `div#root` donde React monta la app.
- `frontend/vite.config.ts`: configuracion de Vite con el plugin de React.
- `frontend/tsconfig.json`: configuracion raiz de TypeScript.
- `frontend/tsconfig.app.json`: configuracion TypeScript para la app del navegador.
- `frontend/tsconfig.node.json`: configuracion TypeScript para archivos de Node/Vite.
- `frontend/.oxlintrc.json`: configuracion de Oxlint.
- `frontend/.gitignore`: archivos y carpetas que Git debe ignorar.
- `frontend/src/main.tsx`: punto de entrada de React; renderiza `App` dentro de `#root`.
- `frontend/src/App.tsx`: componente principal de la interfaz.
- `frontend/src/App.css`: estilos especificos del componente `App`.
- `frontend/src/index.css`: estilos globales cargados por `main.tsx`.
- `frontend/src/assets/hero.png`: imagen principal usada por `App.tsx`.
- `frontend/src/assets/react.svg`: logo de React usado en la pantalla inicial.
- `frontend/src/assets/vite.svg`: logo de Vite usado en la pantalla inicial.
- `frontend/public/favicon.svg`: icono del sitio usado por `index.html`.
- `frontend/public/icons.svg`: sprites SVG usados por enlaces/iconos de la UI.
- `frontend/node_modules`: dependencias instaladas; no se edita manualmente.

## Flujo de trabajo recomendado

1. Abre una terminal para el backend.
2. Ejecuta `cd backend` y luego `npm run start:dev`.
3. Abre otra terminal para el frontend.
4. Ejecuta `cd frontend` y luego `npm run dev`.
5. Edita archivos de `backend/src` para cambiar la API.
6. Edita archivos de `frontend/src` para cambiar la interfaz.
7. Usa `npm run lint` y `npm run test` antes de subir cambios.

## Solucion de problemas

Si falta `node_modules`, ejecuta `npm install` dentro de la carpeta que falle.

Si un puerto esta ocupado:

- Backend: cambia `PORT`.
- Frontend: revisa el puerto que Vite imprime en terminal.

Si quieres limpiar y reinstalar dependencias:

```bash
cd backend
npm install

cd ../frontend
npm install
```

