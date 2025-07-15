# JavaScr

# SPA-

## 🚀 Características

* **Autenticación de Usuarios:** Registro y acceso seguro con dos roles disponibles: Administrador y Visitante.
* **Panel según Rol del Usuario:**

  * **Administrador:** Puede crear, editar y eliminar eventos.
  * **Visitante:** Puede visualizar eventos disponibles, inscribirse y revisar sus inscripciones.
* **Persistencia de Sesión:** La sesión se guarda en LocalStorage y se mantiene después de recargar la página.
* **Rutas Protegidas:** Solo los usuarios autenticados acceden al panel, y las secciones de administrador están restringidas.
* **Interfaz Responsiva:** Diseño moderno, adaptable a dispositivos móviles y fiel a los mockups.
* **SweetAlert2:** Todas las alertas y confirmaciones se manejan con modales estilizados de SweetAlert2.
* **API Local:** Toda la información se gestiona mediante [`json-server`](https://github.com/typicode/json-server), que actúa como una API REST para pruebas.
* **Motor Vite:** Ofrece recarga rápida en tiempo real y herramientas modernas de desarrollo.

---

## 📁 Estructura del Proyecto

```
SPA-Contest/
├── public/
│   └── img/           # Íconos, imágenes de eventos, SVGs
├── src/
│   ├── css/           # Estilos globales y específicos por página
│   ├── components/    # Componentes reutilizables de UI (como EventList)
│   ├── pages/         # Vistas principales (Login, Registro, Panel, etc.)
│   ├── router/        # Lógica de enrutamiento SPA
│   ├── services/      # Abstracción de llamadas a la API
│   ├── utils/         # Funciones auxiliares (auth, sesiones)
│   └── main.js        # Punto de entrada de la aplicación
├── db.json            # Base de datos local para json-server
├── index.html         # HTML principal de la aplicación
├── package.json       # Dependencias y scripts
├── README.md          # Documentación del proyecto
├── PostmanCollection.json # Pruebas API para Postman
└── ...
```

---

## 🛠️ Instalación y Uso

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/MrSantosss/JavaScr
   cd SPA-Contest
   ```

2. **Instalar dependencias:**

   ```bash
   npm install
   ```

3. **Iniciar el servidor de API local (`json-server`):**

   ```bash
   npm run start:server
   ```

   El API estará disponible en [http://localhost:3001](http://localhost:3001)

4. **Iniciar el servidor de desarrollo con Vite:**

   ```bash
   npm run dev
   ```

   La app se ejecutará en [http://localhost:5173](http://localhost:5173) (o el puerto que indique Vite).

5. **Abre la aplicación en tu navegador y comienza a explorar.**

---

## 👤 Usuarios Predeterminados

* **Administrador:**

  * Correo: `admin@admin.com`
  * Contraseña: `admin123`

* **Visitantes:** Puedes registrarte desde la aplicación o utilizar la colección de Postman.

---

## 🧪 Pruebas de API (Postman)

* Importa el archivo `PostmanCollection.json` en Postman.
* Prueba todos los endpoints disponibles: usuarios, eventos e inscripciones (CRUD).
* Se incluyen ejemplos de solicitudes para login, registro, gestión de eventos e inscripciones.

---

## 📝 Resumen de Endpoints

### Usuarios

* `GET /users` — Lista de todos los usuarios
* `POST /users` — Registrar un nuevo usuario
* `GET /users?email=...&password=...` — Iniciar sesión usando las credenciales

### Eventos

* `GET /events` — Obtener todos los eventos
* `POST /events` — Crear evento (solo administrador)
* `PUT /events/:id` — Editar evento (solo administrador)
* `DELETE /events/:id` — Eliminar evento (solo administrador)

### Inscripciones

* `GET /enrollments` — Listar todas las inscripciones
* `POST /enrollments` — Inscribir a un usuario en un evento
* `GET /enrollments?userId=...` — Ver inscripciones por usuario
* `GET /enrollments?eventId=...` — Ver inscripciones por evento

---

## 🖥️ Vistas Principales y Rutas

* **Iniciar Sesión:** `/login` — Autenticación de usuarios
* **Registro:** `/register` — Crear cuenta nueva
* **Panel Principal:** `/dashboard` — Vista de eventos (según el rol)
* **Crear Evento:** `/dashboard/events/create` — Solo para admin
* **Editar Evento:** `/dashboard/events/edit?id=EVENT_ID` — Solo para admin
* **Inscripciones:** `/dashboard/enrollments` — Solo para visitantes
* **No Encontrado:** `/not-found` — Página personalizada 404

---

