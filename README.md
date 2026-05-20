# 🏫 EduGestion API • Backend

[![Node.js Version](https://img.shields.io/badge/node-%3E%3D%2018.x-green.svg?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/express-%23000000.svg?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)](https://jwt.io/)
[![Jest Testing](https://img.shields.io/badge/Jest-C21325?style=for-the-badge&logo=Jest&logoColor=white)](https://jestjs.io/)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg?style=for-the-badge)](https://opensource.org/licenses/ISC)

> **EduGestion** es una API REST robusta, escalable y de alto rendimiento diseñada para la administración integral de instituciones educativas. Facilita la gestión de matrículas, carga académica, calificaciones y la generación automatizada de boletines escolares en PDF, sirviendo como la columna vertebral tecnológica para plataformas educativas modernas.

---

## 🚀 Características Clave

*   **🔐 Autenticación y Seguridad de Nivel Industrial:** Registro e inicio de sesión seguros con cifrado de contraseñas mediante **Bcrypt** y autorización basada en roles utilizando **JSON Web Tokens (JWT)**.
*   **📚 Gestión de Carga Académica:** Asignación flexible de docentes a grupos, sedes y asignaturas específicas.
*   **📝 Registro y Evaluación de Calificaciones:** Control detallado de notas con indicadores de logro personalizados y cálculo de promedios periódicos.
*   **📄 Generación de Boletines en Tiempo Real:** Motor de generación de reportes y boletines en formato PDF de alta densidad utilizando **PDFKit**, listos para impresión o descarga.
*   **✉️ Sistema Automatizado de Notificaciones:** Integración con **Nodemailer** para validación de servicios y envío automático de correos institucionales.
*   **🛡️ Validación Rigurosa de Datos:** Sanitización y validación de payloads en cada endpoint con **Express-Validator** para garantizar la integridad de la base de datos.
*   **🧪 Suite de Pruebas Automatizadas:** Pruebas unitarias y de integración implementadas con **Jest** y **Supertest**, asegurando la estabilidad y resiliencia del software ante refactorizaciones.

---

## 🛠️ Stack Tecnológico

*   **Runtime:** Node.js (v18+)
*   **Framework Web:** Express.js (v5.x - ¡Última generación!)
*   **Base de Datos (NoSQL):** MongoDB
*   **Modelado de Datos:** Mongoose (ODM)
*   **Testing:** Jest & Supertest
*   **Generador de PDF:** PDFKit
*   **Envío de Correo:** Nodemailer
*   **Formato de Módulos:** ES Modules (`import`/`export` nativo)

---

## 📂 Arquitectura del Proyecto (MVC)

El proyecto sigue una estructura limpia, modular y altamente mantenible basada en el patrón de arquitectura **Modelo-Vista-Controlador (MVC)** para el Backend:

```bash
├── 📁 controllers      # Lógica de negocio (procesamiento de peticiones y respuestas)
├── 📁 models           # Esquemas y modelos de datos de Mongoose
├── 📁 routes           # Definición de rutas y endpoints de la API REST
├── 📁 middlewares      # Validadores de JWT, roles y express-validator
├── 📁 services         # Servicios de terceros (Nodemailer, servicios externos)
├── 📁 helpers          # Funciones de ayuda y utilidades reutilizables
├── 📁 utils            # Clases y funciones utilitarias
├── 📁 tests            # Suite completa de pruebas unitarias e integración (Jest/Supertest)
├── 📄 app.js           # Punto de entrada de la aplicación y configuración del servidor
└── 📄 package.json     # Dependencias, metadatos y scripts del proyecto
```

---

## 🚦 Endpoints Principales de la API

La API está documentada y organizada bajo el prefijo `/api/`. A continuación se detallan los módulos principales:

| Entidad | Endpoint Base | Operaciones Soportadas |
| :--- | :--- | :--- |
| **Usuarios** | `/api/users` | Registro, Login, Gestión de Roles (Admin, Docente, Estudiante, etc.) |
| **Carga Académica** | `/api/academicLoad` | Asignación de docentes a materias y grupos |
| **Estudiantes / Matrículas** | `/api/registration` | Procesos de registro e inscripción en periodos escolares |
| **Grupos / Grados** | `/api/groups` | Creación de cursos (ej: 10°A, 11°B), asignación de directores |
| **Calificaciones** | `/api/qualifications` | Registro de notas, edición e histórico académico |
| **Boletines** | `/api/bulletins` | Generación e impresión de reportes académicos en PDF |
| **Indicadores / Logros** | `/api/indicators` | Gestión de indicadores de desempeño académico |
| **Materias** | `/api/subjects` | Creación y administración del pensum académico |

---

## ⚙️ Instalación y Configuración Local

Sigue estos sencillos pasos para levantar el entorno de desarrollo localmente:

### 1. Clonar el repositorio y acceder
```bash
git clone https://github.com/ProyectoAdsoSocorro/Proyecto-final.git
cd Proyecto-final
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Configurar variables de entorno
Crea un archivo `.env` en la raíz del proyecto y añade las siguientes variables:
```env
PORT=3000
MONGO_URL=tu_cadena_de_conexion_a_mongodb
JWT_SECRET=tu_firma_secreta_super_segura
EMAIL_HOST=smtp.tuservicio.com
EMAIL_PORT=587
EMAIL_USER=tu_correo@ejemplo.com
EMAIL_PASS=tu_contraseña_de_aplicacion
```

### 4. Iniciar el servidor
*   **Modo Producción / Inicio rápido:**
    ```bash
    npm start
    ```

---

## 🧪 Control de Calidad: Testing Suite

Para asegurar que cada cambio en el código mantenga la estabilidad del software, la suite de pruebas verifica la integridad del sistema:

*   **Ejecutar todos los tests:**
    ```bash
    npm test
    ```
*   **Ejecutar en modo observador (ideal para desarrollo TDD):**
    ```bash
    npm run test:watch
    ```

---

## 🌟 Buenas Prácticas de Ingeniería Implementadas

*   **Clean Code & SOLID:** Separación estricta de responsabilidades. Los controladores solo manejan HTTP, la lógica compleja reside en servicios y helpers.
*   **Seguridad Activa:** Protección de rutas mediante middlewares de verificación de tokens JWT y validación exhaustiva de roles jerárquicos.
*   **Integridad de Datos:** Validaciones a nivel de base de datos con esquemas estrictos de Mongoose y a nivel de transporte con `express-validator`.
*   **Async/Await:** Código asíncrono limpio y moderno para el manejo fluido de consultas a la base de datos sin incurrir en callback hells.

---

## 👤 Desarrollado por
Este proyecto refleja la aplicación de conceptos avanzados de arquitectura de software, bases de datos NoSQL y buenas prácticas de desarrollo web. 

*   **GitHub:** [kjsanabria](https://github.com/kjsanabria)
*   **LinkedIn:** [Tu Nombre Profesional](https://linkedin.com/in/tu-perfil)

---
*Desarrollado como proyecto de grado con enfoque en la excelencia técnica, la escalabilidad y la automatización de procesos institucionales.*
