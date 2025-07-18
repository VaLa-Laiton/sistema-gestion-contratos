# Estructura del proyecto

/sistema-gestion-contratos/
│
├── app/
│   ├── __init__.py
│   ├── main.py             # <- Orquestador que une los módulos
│   ├── database.py         # <- Lógica de BD compartida
│   ├── dependencies.py     # <- Dependencias compartidas (ej. get_current_user)
│   │
│   ├── core/
│   │   ├── __init__.py
│   │   └── config.py       # <- Configuración global compartida
│   │
│   └── modules/            # <- CARPETA PRINCIPAL PARA MÓDULOS
│       ├── __init__.py
│       │
│       ├── auth/
│       │   ├── __init__.py
│       │   ├── router.py   # Endpoints (/login)
│       │   ├── crud.py     # Lógica de autenticación (opera sobre el modelo de usuario)
│       │   └── schema.py   # Schemas de Token y TokenData
│       │
│       ├── users/
│       │   ├── __init__.py
│       │   ├── model.py    # Modelo SQLAlchemy para la tabla 'users'
│       │   ├── schema.py   # Schemas Pydantic para UserCreate, User, etc.
│       │   ├── crud.py     # Funciones CRUD para usuarios
│       │   └── router.py   # Endpoints (/users, /users/{id}, etc.)
│       │
│       ├── clients/
│       │   ├── __init__.py
│       │   ├── model.py    # Modelo SQLAlchemy para la tabla 'clients'
│       │   ├── schema.py   # Schemas para ClientCreate, etc.
│       │   ├── crud.py     # Funciones CRUD para clientes
│       │   └── router.py   # Endpoints (/clients)
│       │
│       └── contracts/
│           └── # ... (misma estructura: model.py, schema.py, crud.py, router.py)
│
├── Dockerfile
├── docker-compose.yml
└── ... (otros archivos raíz como .env, requirements.txt)
