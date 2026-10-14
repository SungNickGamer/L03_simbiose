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
> 
> ```
> 
> 
> *(Asegúrate de que también se conserve visible el diagrama de E1 en este documento).*

---

### Apartado 5: Respaldo

> * **Requisitos de Usuario (UR) y Funcionales (FR):** Añade los códigos UR y FR que correspondan en tu catálogo de requisitos para los apartados 4.1 al 4.5 del plan E2 (relativos a salud, recetas, accesos de nutricionistas y búsquedas).
> * **Requisitos No Funcionales (NFR):** Especifica las restricciones de privacidad y seguridad en el acceso a los datos médicos (cumplimiento normativo de historiales clínicos).
> * **Acuerdos:** Cita el acta de UR-05 y el acta de acuerdos técnicos y operativos para justificar las reglas de negocio sobre la compartición de datos con profesionales y validación de recetas.
> 
> 

---

### Apartado 6: Descripciones

> *Apartado reservado para la siguiente práctica (L06). Déjalo en blanco o con un texto indicando que se completará en L06 tal como indica la hoja de trabajo.*

---

### Apartado 7: Continuidad

> * **Incorpora en E2:** La gestión completa del historial de salud, el sistema de invitaciones a nutricionistas, el flujo de creación y validación de recetas, y los mecanismos de búsqueda avanzada.
> * **Queda pendiente:** El desarrollo de las descripciones detalladas de los casos de uso (L06) y las preguntas abiertas que las fuentes actuales del proyecto todavía no resuelven del todo (como ciertos detalles límite en la revocación de permisos o restricciones automáticas de recetas).
> 
>
