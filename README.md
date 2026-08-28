# 🛍️ Casinelect

> **Tienda web moderna de electrodomésticos con tecnología de vanguardia**

Casinelect es una plataforma e-commerce completa diseñada para la venta de electrodomésticos, con una experiencia de usuario intuitiva, segura y optimizada para conversión.

---

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Demo](#-demo)
- [Instalación](#-instalación)
- [Requisitos](#-requisitos)
- [Tech Stack](#-tech-stack)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Cómo Usar](#-cómo-usar)
- [API](#-api)
- [Licencia](#-licencia)
- [Autor](#-autor)

---

## ✨ Características

- 🛒 **Carrito de compras** - Gestión completa del carrito
- 💳 **Pagos seguros** - Integración con pasarelas de pago
- 📱 **Diseño Responsive** - Funciona perfectamente en móvil, tablet y desktop
- ⚡ **Alto rendimiento** - Optimizado para velocidad y SEO
- 🔍 **Búsqueda avanzada** - Filtros y búsqueda por categoría
- 👤 **Sistema de usuarios** - Registro, login y perfil de cliente
- 📊 **Panel administrativo** - Gestión de productos e inventario
- 🔒 **Seguridad** - HTTPS, validaciones y protección contra ataques comunes
- 📦 **Gestión de inventario** - Control de stock en tiempo real
- 📧 **Notificaciones** - Confirmación de pedidos por email

---

## 🎬 Demo

🔗 **Sitio en vivo:** [casinelect.com](https://casinelect.com) *(próximamente)*

![Casinelect Demo](https://via.placeholder.com/1200x600?text=Casinelect+Demo)

---

## 🚀 Instalación

### Opción 1: Instalación local

```bash
# Clonar el repositorio
git clone https://github.com/josecasincubero/Casinelect.git
cd Casinelect

# Instalar dependencias
npm install

# Configurar variables de entorno
cp .env.example .env
# Editar .env con tus credenciales

# Iniciar servidor de desarrollo
npm run dev

# La aplicación estará disponible en: http://localhost:3000
```

### Opción 2: Con Docker

```bash
docker-compose up --build
```

---

## 📋 Requisitos

- **Node.js** 16.x o superior
- **npm** 8.x o superior (o yarn/pnpm)
- **PostgreSQL** 13+ (para base de datos)
- **Redis** 6+ (opcional, para caché)

**Versiones recomendadas:**
```
Node.js: 18.x LTS
npm: 9.x
```

---

## 🛠️ Tech Stack

### Frontend
- **React** 18.x - Librería UI
- **Next.js** 13.x - Framework React con SSR
- **Tailwind CSS** - Estilos y diseño responsive
- **Zustand** - Gestión de estado
- **Axios** - Cliente HTTP

### Backend
- **Node.js** + **Express.js** - Servidor web
- **PostgreSQL** - Base de datos principal
- **Prisma** - ORM para gestión de datos
- **JWT** - Autenticación
- **Stripe/PayPal** - Procesamiento de pagos

### DevOps & Herramientas
- **GitHub Actions** - CI/CD
- **Docker** - Containerización
- **ESLint** + **Prettier** - Linting y formato
- **Jest** - Testing
- **Vercel** - Hosting

---

## 📁 Estructura del Proyecto

```
Casinelect/
├── frontend/                 # Aplicación React/Next.js
│   ├── pages/               # Rutas y páginas
│   ├── components/          # Componentes reutilizables
│   ├── styles/              # Estilos globales
│   ├── utils/               # Funciones utilitarias
│   └── public/              # Assets estáticos
├── backend/                 # API Node.js/Express
│   ├── routes/              # Endpoints de API
│   ├── controllers/         # Lógica de negocio
│   ├── models/              # Esquemas de BD
│   ├── middleware/          # Middlewares personalizados
│   └── config/              # Configuraciones
├── database/                # Scripts de BD
│   └── migrations/          # Migraciones Prisma
├── .github/
│   └── workflows/           # GitHub Actions
├── docker-compose.yml       # Composición de servicios
├── .env.example             # Variables de entorno de ejemplo
└── README.md                # Este archivo
```

---

## 🎮 Cómo Usar

### Cliente (Frontend)

1. **Acceder a la tienda**
   ```
   https://localhost:3000
   ```

2. **Buscar productos**
   - Usar la barra de búsqueda o filtros por categoría
   - Ver detalles del producto

3. **Añadir al carrito**
   - Seleccionar cantidad
   - Hacer clic en "Añadir al carrito"

4. **Checkout**
   - Revisar carrito
   - Ingresar datos de envío
   - Procesar pago seguro

5. **Seguimiento**
   - Ver estado del pedido en tu cuenta

### Administrador (Backend)

1. **Acceder al panel**
   ```
   https://localhost:3000/admin
   ```

2. **Gestionar productos**
   - Crear, editar, eliminar productos
   - Actualizar precios e inventario

3. **Gestionar pedidos**
   - Ver pedidos pendientes
   - Actualizar estado de envío
   - Generar reportes

4. **Gestionar usuarios**
   - Ver lista de clientes
   - Gestionar permisos

---

## 🔌 API

### Endpoints principales

**Productos**
```
GET    /api/products              # Listar productos
GET    /api/products/:id          # Obtener producto
POST   /api/products              # Crear (admin)
PUT    /api/products/:id          # Actualizar (admin)
DELETE /api/products/:id          # Eliminar (admin)
```

**Carrito**
```
GET    /api/cart                  # Obtener carrito
POST   /api/cart/items            # Añadir item
PUT    /api/cart/items/:id        # Actualizar cantidad
DELETE /api/cart/items/:id        # Eliminar item
```

**Órdenes**
```
POST   /api/orders                # Crear orden
GET    /api/orders/:id            # Obtener orden
GET    /api/orders                # Listar órdenes del usuario
```

**Usuarios**
```
POST   /api/auth/register         # Registrarse
POST   /api/auth/login            # Iniciar sesión
GET    /api/auth/profile          # Obtener perfil
PUT    /api/auth/profile          # Actualizar perfil
```

---

## 🧪 Testing

```bash
# Ejecutar tests unitarios
npm run test

# Ejecutar tests con cobertura
npm run test:coverage

# Tests E2E
npm run test:e2e
```

---

## 📦 Deployment

### Vercel (Frontend)

```bash
npm run build
vercel
```

### Heroku (Backend)

```bash
heroku create casinelect-api
git push heroku main
```

### Docker

```bash
docker build -t casinelect .
docker run -p 3000:3000 casinelect
```

---

## 📝 Variables de Entorno

Crear archivo `.env` con:

```env
# Base de datos
DATABASE_URL=postgresql://user:password@localhost:5432/casinelect

# Autenticación
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRY=7d

# Pagos
STRIPE_PUBLIC_KEY=pk_test_xxxxx
STRIPE_SECRET_KEY=sk_test_xxxxx

# Email
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_password

# URLs
FRONTEND_URL=http://localhost:3000
API_URL=http://localhost:3001
```

---

## 🤝 Contribuir

Las contribuciones son bienvenidas! Por favor:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

Lee [CONTRIBUTING.md](./CONTRIBUTING.md) para más detalles.

---

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Ver archivo [LICENSE](./LICENSE) para más detalles.

---

## 🐛 Reportar Bugs

¿Encontraste un bug? Abre un [Issue](https://github.com/josecasincubero/Casinelect/issues) describiendo:

- Qué esperabas que sucediera
- Qué sucedió realmente
- Pasos para reproducir el error
- Tu entorno (navegador, SO, versión)

---

## 💬 Soporte

- 📧 Email: support@casinelect.com
- 💬 Discord: [Únete a nuestro servidor](https://discord.gg/casinelect)
- 📖 Documentación: [Wiki](https://github.com/josecasincubero/Casinelect/wiki)

---

## 👤 Autor

**Jose Casincubero**

- GitHub: [@josecasincubero](https://github.com/josecasincubero)
- Email: josecasincubero@gmail.com
- LinkedIn: [Ver perfil](https://linkedin.com/in/josecasincubero)

---

## 🙏 Agradecimientos

- Google AI Studio por la plantilla
- Comunidad de código abierto
- Todos los contribuidores

---

## 📊 Estadísticas

![GitHub stars](https://img.shields.io/github/stars/josecasincubero/Casinelect?style=social)
![GitHub forks](https://img.shields.io/github/forks/josecasincubero/Casinelect?style=social)
![GitHub issues](https://img.shields.io/github/issues/josecasincubero/Casinelect)

---

## 🚀 Roadmap

- [ ] Implementar sistema de recomendaciones
- [ ] Añadir multi-idioma (ES, EN, PT)
- [ ] Integración con WhatsApp
- [ ] App móvil nativa
- [ ] AI chatbot para soporte
- [ ] Programa de afiliados
- [ ] Suscripciones periódicas

---

<div align="center">

⭐ Si te gustó este proyecto, considera darle una estrella! ⭐

</div>