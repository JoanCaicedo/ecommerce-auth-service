# ecommerce-auth-service

🔐 ecommerce-auth-service
Este microservicio se encargará de toda la lógica relacionada con la autenticación y autorización de usuarios en el sistema e-commerce. Es la puerta de entrada a la plataforma, y protegerá los recursos de los demás microservicios mediante la emisión y validación de tokens JWT.

⚙️ Responsabilidades principales:
🧾 Registro de usuarios (/auth/register)
Permitir la creación de cuentas de usuario mediante validaciones seguras y persistencia de datos.

🔐 Login (/auth/login)
Validación de credenciales y generación de JWT (JSON Web Token) con la información del usuario.

🎫 Emisión de tokens seguros
El token incluirá datos esenciales como:

ID de usuario

Rol (CLIENT, ADMIN)

Fecha de expiración

✅ Validación de tokens
Filtrado de peticiones entrantes en microservicios externos mediante filtros de seguridad que validen la firma y vigencia del token.

🛡️ Protección de rutas
Configuración de rutas públicas y privadas según roles y permisos definidos en el token.

👥 Gestión de roles y permisos
Control de acceso a funcionalidades según el tipo de usuario (por ejemplo, solo el admin puede crear productos).

🧰 Tecnologías y herramientas a aplicar:
Spring Boot

Spring Security

JWT (io.jsonwebtoken - jjwt)

BCrypt para hashing de contraseñas

PostgreSQL para persistencia de usuarios

Redis (opcional) para control de sesión o blacklist de tokens

Librerías de validación: @Valid, @NotBlank, @Email, etc.

🧱 Estructura base sugerida:
pgsql
Copiar
Editar
ecommerce-auth-service/
├── controller/
│   └── AuthController.java
├── service/
│   └── AuthService.java
├── dto/
│   ├── AuthRequest.java
│   ├── AuthResponse.java
│   └── RegisterRequest.java
├── model/
│   └── User.java
├── repository/
│   └── UserRepository.java
├── security/
│   ├── JwtTokenProvider.java
│   ├── JwtFilter.java
│   ├── SecurityConfig.java
│   └── CustomUserDetailsService.java
└── application.yml
