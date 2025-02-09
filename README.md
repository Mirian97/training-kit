# Eniwer Training Kit

Eniwer Training Kit es un sistema web diseñado para validar y entrenar personas en entornos de desarrollo full-stack.

### Características

- **Sesiones de usuario:** inicio de sesión seguro bajo estándar OAuth2.
- **Administración de usuarios:** módulo básico para registro y mantenimiento de usuarios.
- **Administración de tareas:** módulo básico para registro y seguimiento de tareas.

### Estructura

- **API**: es el back-end del sistema y provee una interfaz de aplicaciones.
- **Web**: es el front-end del sistema y provee una interfaz gráfica para usuarios.
- **WebSocket**: es el canal de comunicación en tiempo real del sistema.

### Changelog

##### Versión 1.0 (Febrero 2025)

- Primera versión.

## Requisitos

- [PostgreSQL](https://postgresql.org/)
- [git](https://git-scm.com/)
- [PHP](https://php.net/)
- [Composer](https://getcomposer.org/)
- [Node.js](https://nodejs.org/)

## 1. Preparación

#### Clonar Repositorio usando HTTP

```
git clone https://github.com/eniwer/training-kit.git
```

#### Clonar Repositorio usando SSH

```
git clone git@github.com:eniwer/training-kit.git
```

#### Configurar variables de entorno

| Directorio               | Archivo      | Contenido                      |
| ------------------------ | ------------ | ------------------------------ |
| `training-kit/api`       | `.env`       | Variables de entorno Back-end  |
| `training-kit/web`       | `.env.local` | Variables de entorno Front-end |
| `training-kit/websocket` | `.env`       | Variables de entorno WebSocket |

#### Crear base de datos

```
psql -U postgres -c "CREATE DATABASE training;"
```

## 2. Instalación

#### Instalar Back-end

```
cd training-kit/api
composer install
composer setup
```

#### Instalar WebSocket

```
cd tranining-kit/websocket
npm install
```

#### Instalar Front-end

```
cd tranining-kit/web
npm install
```

## 3. Ejecución

#### Iniciar Back-end

```
cd tranining-kit/api
cp .env.example .env
php artisan serve
php artisan key:generate
php artisan migrate:fresh --seed
php artisan install:api --passport
```

#### Iniciar WebSocket

```
cd tranining-kit/websocket
cp .env.example .env
node WebSocket.js
```

#### Iniciar Front-end

```
cd tranining-kit/web
cp .env.local.example .env
npm run dev
```

## 4. Acceso

```
http://localhost:8002
```

> Usuario: debug@eniwer.dev
>
> Contraseña: eniwer

## Licencia

Eniwer Training Kit es un sistema de código abierto desarrollado por ENIWER SpA en Chile bajo licencia GNU GPLv3 (GNU General Public License v3.0).

##### Otras Licencias

- [Vue.js] - Framework Javascript para construir interfaces de usuario.
- [Vue Router] - Librería para gestionar enrutamiento en aplicaciones Vue.js.
- [Vuex] - Librería para gestionar el estado de aplicaciones Vue.js.
- [Laravel] - Framework PHP para construir interfaces de aplicaciones.
- [Laravel Passport] - Librería para implementar OAuth 2.
- [Bootstrap] - Librería CSS para estilizar interfaces gráficas.
- [FontAwesome] - Librería de iconos.
- [Socket.IO] - Librería de comunicación bidireccional de baja latencia.
- [axios] - Cliente HTTP Javascript.
- [vuepic/vue-datepicker] - Librería para implementar calendarios de fechas.

  [Vue.js]: http://vuejs.org
  [Vuex]: https://vuex.vuejs.org/
  [Vue Router]: https://router.vuejs.org
  [Laravel]: https://laravel.com/
  [Laravel Passport]: https://laravel.com/docs/11.x/passport
  [Bootstrap]: https://getbootstrap.com
  [FontAwesome]: https://fontawesome.com
  [Socket.IO]: https://socket.io
  [axios]: https://axios-http.com
  [vuepic/vue-datepicker]: https://vue3datepicker.com
