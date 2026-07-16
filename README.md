# SIGCA · AOMA Seccional San Juan

Primera versión navegable del Sistema Integral de Gestión, Capacitación y Administración Sindical. Esta entrega convierte el Documento Maestro v1.0 en una interfaz institucional responsive y establece una base compatible con Vercel.

## Alcance de esta versión

- Dashboard institucional adaptado a escritorio, tablet y celular.
- Navegación de Afiliaciones, Gestión institucional, Organización, Academia, Documentación, Informes y Administración.
- Indicadores, tareas prioritarias, agenda y compromisos activos.
- Búsqueda interactiva, selector de vista por rol y avisos de acciones.
- Identidad visual basada en azul petróleo, grafito, blanco, dorado y naranja AOMA.
- Conexión preparada con el proyecto Supabase histórico.
- Catálogo inicial recuperado: leyes, convenios y curso de negociación colectiva.

Los indicadores del tablero siguen siendo demostrativos. La autenticación histórica, las tablas `usuarios`, `empresas` y `convenios`, y las funciones existentes de Supabase quedaron documentadas y tipadas para su integración progresiva.

## Supabase

El repositorio incluye `.env.production` con la URL y la clave pública anónima necesarias para el despliegue inicial. Para desarrollo local puede copiarse como `.env.local`. Nunca debe utilizarse una clave `service_role` en componentes del navegador ni guardarla en el repositorio.

La capa de acceso se encuentra en `lib/supabase/` y conserva como punto de partida las tablas `usuarios`, `empresas` y `convenios`, junto con las funciones `actualizar_mi_perfil` y `administrar_usuario`. Antes de habilitar altas o cambios se deben revisar las políticas RLS del proyecto Supabase.

## Desarrollo local

Requisitos: Node.js 22 o superior y pnpm.

```bash
pnpm install
pnpm dev
```

Abrir `http://localhost:3000`.

## Verificación

```bash
pnpm typecheck
pnpm build
```

## Despliegue en Vercel

1. Importar el repositorio desde GitHub en Vercel.
2. Vercel detectará Next.js automáticamente.
3. No se requieren variables de entorno para esta primera versión.
4. Publicar primero como entorno de vista previa para validación institucional.

## Próxima fase recomendada

Implementar autenticación, PostgreSQL, roles y permisos granulares, empresas y proyectos, solicitudes de acceso con vencimiento, auditoría básica y la base del flujo de afiliaciones.
