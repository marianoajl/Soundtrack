(# Manual de Usuario — SoundTrack)

## Descripción General
SoundTrack es una aplicación web para la gestión de equipos de audio, despachos y logística de eventos. Permite administrar inventario, usuarios, ubicaciones y movimientos de equipos, con control de acceso por perfiles.

---

## Tipos de Perfiles de Usuario

La aplicación define los siguientes perfiles:

- **Administrador (admin):** Acceso total. Puede gestionar usuarios, equipos, ubicaciones y despachos.
- **Depósito (deposito):** Puede gestionar equipos, ubicaciones y despachos, pero no usuarios.
- **Viewer:** Solo puede visualizar información (mapa, despachos, equipos), sin editar.
- **Transportista (driver):** Solo accede a la vista "Mis Viajes" con los despachos asignados.

---

## Reglas de Negocio

- **Inventario:** Cada equipo tiene una cantidad total. El sistema controla disponibilidad y evita sobreasignación en despachos.
- **Despachos:** Un despacho tiene origen, paradas (destinos), equipos y fechas. No se puede crear un despacho si hay conflicto de disponibilidad.
- **Ubicaciones:** Pueden ser de tipo "Depósito" o "Lugar de show". Se geolocalizan y pueden buscarse por dirección.
- **Usuarios:** El registro estándar crea usuarios tipo Viewer. Solo el admin puede crear usuarios de otros perfiles.
- **Contraseñas:** Deben tener al menos 8 caracteres, mayúscula, minúscula, número y carácter especial.
- **Validaciones:** El sistema valida correos, teléfonos y evita duplicados.

---

## Ítems del Menú Lateral (según perfil)

| Perfil        | Ítems del menú lateral                      |
|--------------|---------------------------------------------|
| Admin        | Mapa, Despachos, Lugares, Equipos, Usuarios |
| Depósito     | Mapa, Despachos, Lugares, Equipos           |
| Viewer       | Mapa, Despachos, Equipos                    |
| Transportista| Mis Viajes                                  |

---

## Uso de la Aplicación

### 1. **Ingreso y Registro**
- Login con usuario y contraseña.
- Registro estándar: nombre, apellido, teléfono, correo y contraseña (Viewer).
- El admin puede crear usuarios de cualquier perfil.

### 2. **Mapa de Ubicaciones**
- Visualiza todos los puntos registrados (depósitos y lugares de show).
- Permite ver equipos presentes en cada ubicación y detalles de despachos activos o próximos.
- El usuario puede ver su propia ubicación si otorga permisos de geolocalización.

### 3. **Gestión de Equipos**
- Visualización y filtrado por categoría.
- Admin y depósito pueden agregar, editar o eliminar equipos.
- Muestra cantidad total, en campo y disponible.

### 4. **Gestión de Lugares**
- Solo admin y depósito pueden agregar, editar o eliminar ubicaciones.
- Búsqueda de dirección con autocompletado y geolocalización.

### 5. **Despachos**
- Visualización de todos los despachos (según perfil).
- Creación/edición: origen, paradas, equipos, fechas, conductor y notas.
- Control de disponibilidad de equipos en tiempo real.
- Exportación/impresión de detalles de despacho.

### 6. **Gestión de Usuarios**
- Solo visible para admin.
- Permite crear, editar y eliminar usuarios de cualquier perfil.

### 7. **Mis Viajes**
- Vista exclusiva para transportistas.
- Muestra solo los despachos asignados al usuario para la semana en curso.

---

## Observaciones Técnicas y de Desarrollo

- **Tecnología:** HTML, CSS, JavaScript puro, sin backend ni base de datos persistente (los datos están en memoria en el frontend).
- **Componentes:** Uso de Web Components para cada vista principal.
- **Mapa:** Integración con Leaflet y OpenStreetMap para geolocalización.
- **Responsive:** Interfaz adaptada para escritorio, tablet y móvil. Menú lateral en desktop, menú inferior en móvil.
- **Validaciones:** Formularios con validaciones en tiempo real y mensajes claros.
- **Impresión/Exportación:** Los despachos pueden imprimirse/exportarse en formato amigable.
- **Limitaciones:** Al no tener backend, los datos se pierden al recargar la página.

---

## Glosario Rápido

- **Despacho:** Movimiento de equipos desde un origen a uno o más destinos.
- **Parada:** Cada destino dentro de un despacho.
- **Equipo en campo:** Equipos que están fuera del depósito, asignados a despachos activos.

---

## Contacto y Soporte
Para dudas o soporte, contactar al administrador del sistema.
