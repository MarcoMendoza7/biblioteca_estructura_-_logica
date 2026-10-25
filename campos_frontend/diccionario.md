# DICCIONARIO ... Constantes y Variables. 

## Variables de Usuario y Autenticación

- **login**
  - **Tipo:** STRING
  - **Alias anteriores:** usuario, usuario_Correo, usuario (o correo institucional)
  - **Descripción:** Usuario o correo institucional para login
  - **Se usa en:** Módulo 1
  - **Ejemplo:** "juan.perez@tesjo.edu.mx"

- **contrasena**
  - **Tipo:** STRING
  - **Alias anteriores:** contraseña
  - **Descripción:** Contraseña en texto plano (se cifra en back)
  - **Se usa en:** Módulo 1

- **codigoUsuario**
  - **Tipo:** STRING
  - **Alias anteriores:** matricula, num_empleado, matricula / num_empleado, matricula_o_clave_usuario, responsable_del_adeudo
  - **Descripción:** Identificador único del usuario. Es matrícula para alumnos o número de empleado para docentes/personal. Es LA MISMA variable en todos los módulos
  - **Se usa en:** Módulo 2, 3, 5, 6, 7

- **nombre**
  - **Tipo:** STRING
  - **Alias anteriores:** nombre, nombre_completo, nombre_responsable
  - **Descripción:** Nombre completo del usuario
  - **Se usa en:** Módulo 2, 3, 5, 6

- **tipoUsuario**
  - **Tipo:** STRING - Valores: ALUMNO, DOCENTE, PERSONAL, VISITANTE
  - **Alias anteriores:** tipo_usuario
  - **Descripción:** Tipo de usuario que ingresa a biblioteca
  - **Se usa en:** Módulo 2, 3

- **carreraArea**
  - **Tipo:** STRING
  - **Alias anteriores:** carrera_o_area, carrera_area, carrera_o_especialidad, carrera_o_sector, area_o_carrera, carrera_o_area_solicitante
  - **Descripción:** Carrera del alumno o área de adscripción del docente/personal
  - **Se usa en:** Módulo 2, 3, 5, 7, 8, 9

- **estadoUsuario**
  - **Tipo:** STRING - Valores: ACTIVO, SUSPENDIDO, BAJA, INSCRITO
  - **Alias anteriores:** estado_usuario
  - **Descripción:** Estado actual del usuario en el sistema
  - **Se usa en:** Módulo 2, 3

## Variables de Control de Acceso

- **rfidTag**
  - **Tipo:** STRING
  - **Alias anteriores:** tag_rfid, id_Tag, clave_o_tag
  - **Descripción:** ID único del tag RFID leído por el sensor del usuario
  - **Se usa en:** Módulo 2, 3

- **idTemporal**
  - **Tipo:** STRING
  - **Alias anteriores:** identificador
  - **Descripción:** Identificador temporal/manual para visitantes sin matrícula
  - **Se usa en:** Módulo 2

- **motivo**
  - **Tipo:** STRING
  - **Alias anteriores:** asunto_o_motivo, motivo, motivo_de_la_solicitud
  - **Descripción:** Motivo de la visita a la biblioteca
  - **Se usa en:** Módulo 2, 9

## Variables de Catálogo Bibliográfico

- **materialId**
  - **Tipo:** STRING
  - **Alias anteriores:** id_material, ejemplar_id
  - **Descripción:** ID interno del material bibliográfico
  - **Se usa en:** Módulo 4, 5

- **rfidTagLibro**
  - **Tipo:** STRING
  - **Alias anteriores:** tag_rfid_libro
  - **Descripción:** Tag RFID pegado al libro físico
  - **Se usa en:** Módulo 4, 5

- **titulo**
  - **Tipo:** STRING
  - **Alias anteriores:** titulo, titulo_solicitado
  - **Descripción:** Título del libro o material
  - **Se usa en:** Módulo 4, 9

- **autor**
  - **Tipo:** STRING
  - **Alias anteriores:** autor_autores, autor
  - **Descripción:** Autor o autores del material
  - **Se usa en:** Módulo 4, 9

- **tipoMaterial**
  - **Tipo:** STRING
  - **Alias anteriores:** tipo_de_material
  - **Descripción:** Libro, revista, tesis, manual, etc.
  - **Se usa en:** Módulo 4

- **clasificacion**
  - **Tipo:** STRING
  - **Alias anteriores:** clasificacion
  - **Descripción:** Clasificación Dewey o interna
  - **Se usa en:** Módulo 4

- **editorial**
  - **Tipo:** STRING
  - **Alias anteriores:** editorial
  - **Descripción:** Editorial del libro
  - **Se usa en:** Módulo 4

- **fechaPublicacion**
  - **Tipo:** NUMBER
  - **Alias anteriores:** anio_publicacion
  - **Descripción:** Año de publicación
  - **Se usa en:** Módulo 4

- **isbn**
  - **Tipo:** STRING
  - **Alias anteriores:** isbn
  - **Descripción:** ISBN del libro
  - **Se usa en:** Módulo 4

- **descripcion**
  - **Tipo:** STRING
  - **Alias anteriores:** descripcion
  - **Descripción:** Descripción o resumen del material
  - **Se usa en:** Módulo 4

- **claveGenerada**
  - **Tipo:** STRING
  - **Alias anteriores:** clave_generada
  - **Descripción:** Clave de gerencia o área asignada
  - **Se usa en:** Módulo 4

- **ubicacion**
  - **Tipo:** STRING
  - **Alias anteriores:** ubicacion_fisica
  - **Descripción:** Ubicación física en estantería
  - **Se usa en:** Módulo 4

- **total / cantidad**
  - **Tipo:** NUMBER
  - **Alias anteriores:** stock / ejemplares_totales, disponibilidad_material, disponibilidad
  - **Descripción:** Total de ejemplares y cuantos están disponibles
  - **Se usa en:** Módulo 4, 5

## Variables de Préstamos, Devoluciones y Adeudos

- **idPrestamo**
  - **Tipo:** STRING
  - **Alias anteriores:** id_prestamo, prestamo_relacionado_id
  - **Descripción:** ID único del préstamo, autogenerado
  - **Se usa en:** Módulo 5, 6, 7

- **personalBiblioteca**
  - **Tipo:** STRING
  - **Alias anteriores:** responsable_atencion
  - **Descripción:** Personal bibliotecario que atendió el préstamo
  - **Se usa en:** Módulo 5

- **fechaPrestamo / fechaDevolucion / fechaVencimiento / fechaLimite**
  - **Tipo:** DATE (ISO 8601: YYYY-MM-DD)
  - **Alias anteriores:** fecha_prestamo, fecha_limite_devolucion, fecha_devolucion, fecha_vencimiento, nueva_fecha_limite, fecha_inicio, fecha_fin, fecha_de_solicitud
  - **Descripción:** Fechas clave del ciclo de préstamo
  - **Se usa en:** Módulo 5, 6, 7, 8, 9

- **tipoPrestamo**
  - **Tipo:** STRING - Valores: SALA, DOMICILIO
  - **Alias anteriores:** tipo_de_prestamo
  - **Descripción:** Si el libro se queda en sala o se lleva a casa
  - **Se usa en:** Módulo 5

- **condiciones**
  - **Tipo:** STRING - Valores: EXCELENTE, BUENO, CON_DETALLES, DAÑADO
  - **Alias anteriores:** estado_fisico_del_material, estado_fisico_al_devolver, estado_del_material
  - **Descripción:** Estado físico del libro al prestar y al devolver
  - **Se usa en:** Módulo 5, 6, 7

- **idDevolucion**
  - **Tipo:** STRING
  - **Alias anteriores:** id_devolucion
  - **Descripción:** ID de la devolución
  - **Se usa en:** Módulo 6

- **danio**
  - **Tipo:** STRING
  - **Alias anteriores:** observacion_danio
  - **Descripción:** Observación si el libro regresó dañado
  - **Se usa en:** Módulo 6

- **renovacion**
  - **Tipo:** NUMBER
  - **Alias anteriores:** contador_de_renovaciones
  - **Descripción:** Cuántas veces se ha renovado el préstamo
  - **Se usa en:** Módulo 6

- **sanciones / fechaSancion**
  - **Tipo:** STRING / NUMBER
  - **Alias anteriores:** dias_de_atraso, estado_de_adeudo, semaforo_alerta, estado_de_adeudo
  - **Descripción:** Control de sanciones: días de atraso, estado (Sancionado/Multa/Alerta) y semáforo Verde/Amarillo/Rojo
  - **Se usa en:** Módulo 7

## Variables de Reportes y Solicitudes

- **tipoReporte**
  - **Tipo:** STRING - Valores: INGRESO, SALIDA, MATERIAL, PRESTAMOS, DEVOLUCIONES, HISTORIAL
  - **Alias anteriores:** tipo_reporte
  - **Descripción:** Tipo de reporte a generar
  - **Se usa en:** Módulo 8

- **idSolicitud**
  - **Tipo:** STRING
  - **Alias anteriores:** id_solicitud
  - **Descripción:** ID de solicitud de material no encontrado
  - **Se usa en:** Módulo 9

- **estadoSolicitud**
  - **Tipo:** STRING - Valores: PENDIENTE, EN_TRAMITE, APROBADA, RECHAZADA
  - **Alias anteriores:** estado_solicitud
  - **Descripción:** Estado de la solicitud de libro
  - **Se usa en:** Módulo 9

- **observacion**
  - **Tipo:** STRING
  - **Alias anteriores:** observaciones
  - **Descripción:** Observaciones generales de la solicitud
  - **Se usa en:** Módulo 9
