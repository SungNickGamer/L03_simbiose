Para resolver la práctica y saber exactamente qué redactar en tu archivo `docs/modelos/modelo-casos-de-uso.md`, aquí tienes el contenido estructurado que debes redactar (basado en lo que pide E2 para salud, recetas, búsqueda y ayuda):

---

### Apartado 1: Alcance

> Esta vista de E2 modela los requisitos de la iteración E2 del Proyecto Simbiosis, abriendo el foco hacia la **gestión de la salud e historial**, el **acceso autorizado e invitación al nutricionista**, la **creación y validación de recetas**, la **búsqueda y consulta**, la **identidad pública** y el **sistema de ayuda**. Se conserva íntegro el alcance de E1 (acceso, cuentas y ayuda básica) y quedan pendientes para iteraciones futuras las implementaciones técnicas profundas, la pasarela de pagos completa o las notificaciones avanzadas en tiempo real.

---

### Apartado 2: Actores

> Se mantienen los actores principales de E1 (como el *Paciente/Cliente*) y se incorporan o ajustan los actores específicos que participan en esta iteración según el plan E2:
> * **Paciente / Usuario**: Gestiona su perfil de salud, recetas, consultas y comparte datos con su nutricionista.
> * **Nutricionista / Profesional**: Acepta invitaciones, valida recetas y consulta historiales autorizados.
> * **Administrador**: Gestiona roles, catálogos y validaciones globales del sistema.
> 
> 

---

### Apartado 3: Casos de uso

Debes añadir los siguientes casos de uso nuevos (comenzando a partir de `UC-12`) en una tabla con su ID, nombre, objetivo y participantes:

| ID | Nombre del Caso de Uso | Objetivo | Participantes |
| --- | --- | --- | --- |
| **UC-12** | Consultar Historial de Salud | Permitir al paciente registrar y consultar sus métricas y evolución de salud. | Paciente |
| **UC-13** | Invitar a Nutricionista | Permitir al paciente dar acceso autorizado a un profesional para ver su historial. | Paciente, Nutricionista |
| **UC-14** | Crear Receta | Permitir al usuario o nutricionista redactar y guardar una nueva receta. | Paciente / Nutricionista |
| **UC-15** | Validar Receta | Revisar y aprobar una receta creada bajo criterios nutricionales o de moderación. | Nutricionista / Administrador |
| **UC-16** | Buscar y Consultar Recetas/Salud | Encontrar recetas o información de salud mediante filtros y términos clave. | Usuario, Sistema |
| **UC-17** | Gestionar Identidad Pública | Mostrar y configurar los datos públicos del perfil del profesional o usuario. | Usuario / Nutricionista |

*(Nota: Si en tu diagrama usaste relaciones `<<include>>` o `<<extend>>` para estos casos, asegúrate de documentarlos aquí si el formato de E1 lo requería).*

---

### Apartado 4: Diagramas


> ![Diagrama de Casos de Uso - Salud y Recetas E2](imagenes/casos-de-uso-salud-recetas-e2.png)

---

### Apartado 5: Respaldo

> * **Requisitos de Usuario (UR) y Funcionales (FR):** Añade los códigos UR y FR que correspondan en tu catálogo de requisitos para los apartados 4.1 al 4.5 del plan E2 (relativos a salud, recetas, accesos de nutricionistas y búsquedas).
> * **Requisitos No Funcionales (NFR):** Especifica las restricciones de privacidad y seguridad en el acceso a los datos médicos (cumplimiento normativo de historiales clínicos).
> * **Acuerdos:** Cita el acta de UR-05 y el acta de acuerdos técnicos y operativos para justificar las reglas de negocio sobre la compartición de datos con profesionales y validación de recetas.
> 
> 

---

### Apartado 6: Descripciones

### 6.1. UC-05 Actualizar perfil
* **Identificador y Nombre:** UC-05 Actualizar perfil
* **Descripción / Objetivo:** Permitir al usuario modificar los datos personales de su perfil de cuenta en el sistema.
* **Actor(es) / Participante(s):** Cliente
* **Precondiciones:** El usuario ha iniciado sesión en el sistema.
* **Postcondiciones:** Los datos del perfil del usuario quedan actualizados y guardados en el sistema.
* **Escenario principal de éxito:**
  1. El usuario solicita actualizar su perfil.
  2. El sistema muestra el formulario con los datos actuales del perfil.
  3. El usuario modifica los datos deseados y pulsa en guardar.
  4. El sistema valida los datos introducidos.
  5. El sistema guarda los cambios y muestra un mensaje de éxito.
* **Extensiones (Flujos alternativos):**
  * **3a. El usuario cancela la actualización:**
    * 3a.1. El usuario pulsa cancelar antes de guardar.
    * 3a.2. El caso de uso finaliza sin guardar cambios.
  * **4a. Datos no válidos:**
    * 4a.1. El sistema detecta datos incorrectos o incompletos.
    * 4a.2. El sistema muestra un mensaje de error indicando qué campos son erróneos.
    * 4a.3. El flujo regresa al paso 3 para que el usuario corrija los datos.
  * **5a. Fallo de guardado:**
    * 5a.1. Se produce un error técnico al intentar almacenar los datos en el servidor.
    * 5a.2. El sistema muestra un aviso de error técnico y permite reintentar o cancelar.
* **Requisitos especiales (NFR):** *(Copia aquí exactamente los NFR del apartado 5 de tu documento)*
* **Frecuencia de uso:** Ocasional.
* **Puntos abiertos:** Ninguno.

### 6.2. UC-21 Buscar recetas
* **Identificador y Nombre:** UC-21 Buscar recetas
* **Descripción / Objetivo:** Permitir al usuario buscar recetas aplicando diferentes criterios de filtrado y consultar el detalle de una de ellas.
* **Actor(es) / Participante(s):** Cliente
* **Precondiciones:** El usuario se encuentra en la sección de búsqueda de recetas.
* **Postcondiciones:** Se muestra en pantalla el detalle de la receta seleccionada por el usuario tras la búsqueda.
* **Escenario principal de éxito:**
  1. El usuario solicita buscar recetas indicando un ingrediente.
  2. El sistema aplica el filtro y busca las recetas que contienen dicho ingrediente.
  3. El sistema muestra la lista de resultados obtenidos.
  4. El usuario selecciona una receta de la lista para ver su información.
  5. El sistema muestra los detalles completos de la receta seleccionada.
* **Extensiones (Flujos alternativos):**
  * **1a. Búsqueda por palabra, frase o exclusión:**
    * 1a.1. El usuario introduce texto libre, excluye ingredientes concretos o combina múltiples criterios conforme a lo especificado en el acta.
    * 1a.2. El sistema procesa la combinación de criterios y continúa en el paso 3.
  * **3a. No hay resultados:**
    * 3a.1. El sistema no encuentra ninguna receta que cumpla con los criterios introducidos.
    * 3a.2. El sistema muestra un mensaje indicando que no hay resultados y el caso de uso finaliza.
  * **Conflictos, ausencia de criterios y fallos técnicos:**
    * *(Añade aquí las excepciones adicionales si constan en tu acta)*.
* **Requisitos especiales (NFR):** *(Copia aquí exactamente los NFR del apartado 5 de tu documento)*
* **Frecuencia de uso:** Frecuente.
* **Puntos abiertos:** El alcance de esta descripción es parcial; las demás funciones de UC-21 siguen pendientes y se conservan en el modelo.
---

### Apartado 7: Continuidad

* **Descripciones incorporadas:** Se han incorporado al modelo las descripciones detalladas de UC-05 Actualizar perfil y UC-21 Buscar recetas.
* **Alcance pendiente:** Las demás funciones avanzadas o secundarias de UC-21 siguen pendientes y se conservan en el modelo para futuras iteraciones.
* **Declaración de IA:** No se ha utilizado inteligencia artificial en la realización de la actividad L06.
> 
>
