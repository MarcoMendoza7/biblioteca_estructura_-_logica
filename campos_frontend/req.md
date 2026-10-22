# Datos enviados por FRONT (campos) ... request

## 1. INICIO DE SESIÓN Y AUTENTICACIÓN

### **Login (Usuarios - Docentes - Administrativos)**
**Método**
-       POST(crea token)
- **Datos recibidos (Request Payload):**
  - usuario (nombre o correo institucional)
  - contraseña
- **Datos devueltos (Response / Payload):**
  - token - rol (Administrador / Técnico)
  - datos de perfil del usuario administrativo

## 2. CONTROL DE ACCESO (BITÁCORA Y ENTRADAS)

### **Registro de Acceso (Automático por RFID o Manual)**
**Método**
-       POST(registrar entradas)
-       GET(consultar bitácora)
- **Datos recibidos (Request Payload):**
  - tag_rfid (id leído del TAG por sensor)
  - matricula - num_empleado (en caso de ingreso manual)
  - nombre (manual)
  - tipo_usuario (Alumno, Docente/Personal, Visitante)
  - carrera_o_area (Carrera o área)
  - estado_usuario (Activo, Suspendido, Bajas)
  - identificador (manual / temporal)
  - asunto_o_motivo (Motivo de visita)

## 3. GESTIÓN / REVISIÓN DE USUARIOS

### **Consulta y Modificación de Usuarios**
**Método**
-       GET(buscar, listar o buscar por id usuarios)
-       PUT(actualizar usuario completo)
-       PATCH(actualizar estado)
- **Filtros de Búsqueda (Query Params):**
  - matricula
  - clave_o_tag
  - nombre
- **Campos de Visualización / Edición (Request/Response):**
  - matricula / num_empleado
  - nombre_completo
  - tipo_usuario (Alumno, Docente, Visitante)
  - carrera_area
  - estado_usuario (Inscrito, Suspendido, Dado de baja)
  - historial_prestamos / historial_sanciones

## 4. CATÁLOGO BIBLIOGRÁFICO (RECURSOS / LIBROS)

### **Registro / Edición de Material Bibliográfico**
**Método**
-       POST(crear objetos)
-       GET(buscar, listar o buscar por id)
-       PUT(actualizar objeto)
-       DELETE(eliminar material)
- **Datos recibidos para Creación/Edición (Request Payload):**
  - id_material / tag_rfid_libro
  - titulo
  - autor_autores
  - tipo_de_material
  - clasificacion
  - editorial
  - anio_publicacion
  - isbn
  - descripcion
  - clave_gerencia / asignacion_o_area
  - ubicacion_fisica
  - stock / ejemplares_totales
### **Consulta de Catálogo**
- **Filtros de Búsqueda (Query Params):**
  - titulo
  - autor
  - isbn / clasificacion
  - disponibilidad (Disponible / Prestado)

## 5. MÓDULO DE PRÉSTAMOS

### **Registro de Préstamo**
**Método**
-       POST(crearprestamos)
        GET(consultar prestamos activos)
- **Datos recibidos (Request Payload):**
  - id_prestamo (generado aut.)
  - responsable_atencion
  - matricula_o_clave_usuario
  - carrera_o_especialidad
  - ejemplar_id / tag_rfid_libro
  - fecha_prestamo
  - fecha_limite_devolucion
  - tipo_de_prestamo (Sala / Domicilio)
  - estado_fisico_del_material (Excelente, Bueno, Con detalles)
  - disponibilidad_material

## 6. DEVOLUCIONES Y RENOVACIONES

### **Proceso de Devolución**
**Método**
-       POST(crear devoluciones)
-       PUT(realizar renovaciones)
- **Datos recibidos (Request Payload):**
  - id_devolucion
  - id_prestamo
  - matricula_o_clave_usuario
  - nombre_responsable
  - fecha_devolucion
  - estado_fisico_al_devolver
  - observacion_danio (en caso de daño)
- **Módulo/Pantalla:** Renovación
- **Datos recibidos (Request Payload):**
  - id_prestamo
  - nueva_fecha_limite
  - contador_de_renovaciones (+1)

## 7. ADEUDOS Y ALERTAS (SANCIONES)

### **Control de Adeudos**
**Método**
-       GET(consultar listas de adeudos)
-       POST(generar sanciones)
-       PUT(liquidar o modificar adeudos)
- **Datos manejados (Response / Request):**
  - responsable_del_adeudo (ID Usuario / Matrícula)
  - carrera_o_sector
  - prestamo_relacionado_id
  - estado_del_material
  - fecha_vencimiento
  - dias_de_atraso
  - estado_de_adeudo (Sancionado / Multa / Alerta)
  - semaforo_alerta (Verde: Estable, Amarillo: Se acerca fecha, Rojo: Adeudo)

## 8. REPORTES E HISTORIAL

### **Generación de Reportes**
**Método**
-       GET(consultar reportes)
- **Filtros de consulta (Query Params):**
  - tipo_reporte (Ingreso/Salida, Registro de Material, Préstamos, Devoluciones, Historial)
  - fecha_inicio
  - fecha_fin
  - area_o_carrera

## 9. SOLICITUD DE MATERIAL BIBLIOGRÁFICO

### **Registro de Solicitud (Libros no encontrados)**
**Método**
-       GET(consultar solicitudes)
-       POST(crear solicitudes)
-       PATCH (cambiar estado de solicitud a ... Aprobada - Rechazada)
- **Datos recibidos (Request Payload):**
  - id_solicitud
  - titulo_solicitado
  - autor
  - carrera_o_area_solicitante
  - motivo_de_la_solicitud
  - fecha_de_solicitud
  - estado_solicitud (Pendiente, En Trámite, Aprobada, Rechazada)
  - observaciones

  > Para ver la definición de cada variable, ver ... [Diccionario de Datos](./diccionario.md)
