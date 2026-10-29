# Historias de usuario de búsqueda: Proyecto Simbiosis

* **Versión:** 5.0
* **Fecha:** 27/10/2026
* **Estado:** Borrador

---

## 1. Épica de búsqueda

* **Necesidad conjunta:** Permitir a las personas usuarias buscar recetas en el sistema mediante una palabra o frase descriptiva, filtrando los resultados al incluir determinados ingredientes y excluyendo aquellos que no se deseen consumir.
* **Descomposición:** La épica se encuentra descompuesta en tres historias de usuario: **US-01**, **US-02** y **US-03**. La división se ha realizado separando la capacidad de búsqueda textual principal de la capacidad de refinar los resultados mediante la inclusión de ingredientes obligatorios y la exclusión de alérgenos o ingredientes no deseados, asegurando que cada historia aporte un resultado útil por sí misma.

---

## 2. Historias de usuario y criterios de aceptación

### US-01: Búsqueda por palabra o frase
* **Identificadores y trazabilidad:** UR-08, UC-21, FR-085, apartado del acta correspondiente a búsqueda textual.
* **Redacción:** Como persona aficionada a la cocina, quiero buscar recetas introduciendo una palabra o frase, para encontrar platos relacionados con mis intereses culinarios.
* **Criterios de aceptación:**
  1. Dado que existen recetas registradas en el sistema, cuando la persona introduce la frase "tarta de manzana" en la barra de búsqueda y pulsa buscar, entonces el sistema muestra un listado con todas las recetas cuyo título o descripción coinciden con dicha frase.
  2. Dado que el sistema está operativo, cuando la persona realiza una búsqueda introduciendo un término sin coincidencias (por ejemplo, "recetaimposiblexyz"), entonces el sistema muestra la interfaz de ayuda indicando que no se han encontrado resultados (FR-102).
  3. Dado que existen recetas con tildes y mayúsculas, cuando la persona busca "TARTA", entonces el sistema devuelve los resultados correctos ignorando mayúsculas y diferencias de acentuación.

#### Revisión INVEST (US-01):
* **Independiente:** Sí. Puede implementarse y ofrecer valor por sí sola sin depender de los filtros de ingredientes.
* **Negociable:** Sí. Permite discutir detalles de la interfaz y ordenación de resultados.
* **Valiosa:** Sí. Permite al usuario localizar recetas de forma rápida mediante texto libre.
* **Estimable:** Sí. Alcance acotado y bien definido.
* **Pequeña:** Sí. Se centra exclusivamente en la búsqueda textual básica y gestión de sin resultados.
* **Comprobable:** Sí. Sus criterios describen entradas y resultados observables claros.

---

### US-02: Búsqueda por ingredientes incluidos
* **Identificadores y trazabilidad:** UR-08, UC-21, FR-086, apartado del acta correspondiente a inclusión de ingredientes.
* **Redacción:** Como persona con ingredientes específicos en la nevera, quiero buscar recetas indicando qué ingredientes deben incluir obligatoriamente, para aprovechar los alimentos disponibles.
* **Criterios de aceptación:**
  1. Dado que existen recetas en el catálogo, cuando la persona selecciona los ingredientes "pollo" y "patatas", entonces el sistema muestra únicamente las recetas que contienen ambos ingredientes de forma simultánea.
  2. Dado que el sistema requiere al menos un ingrediente válido, cuando la persona intenta buscar seleccionando únicamente ingredientes mal escritos o vacíos, entonces el sistema muestra un mensaje de aviso sobre la selección.
  3. Dado que se realiza una búsqueda combinada, cuando la persona introduce el texto "asado" y selecciona el ingrediente obligatorio "pollo", entonces el sistema devuelve las recetas que cumplen ambas condiciones de manera conjunta.

#### Revisión INVEST (US-02):
* **Independiente:** Sí. Comparte la infraestructura de datos pero aporta una capacidad de filtrado autónoma.
* **Negociable:** Sí. Deja margen para decidir cómo se seleccionan los ingredientes en la interfaz.
* **Valiosa:** Sí. Facilita el aprovechamiento de los alimentos disponibles en el hogar.
* **Estimable:** Sí. Requisitos y datos claros para su estimación.
* **Pequeña:** Sí. Acotada a la inclusión obligatoria de ingredientes y su combinación con texto.
* **Comprobable:** Sí. Permite verificar de forma directa si las recetas devuelven los ingredientes exigidos.

---

### US-03: Exclusión de ingredientes
* **Identificadores y trazabilidad:** UR-08, UC-21, FR-087, apartado del acta correspondiente a exclusión de ingredientes.
* **Redacción:** Como persona con restricciones alimentarias o alergias, quiero excluir ingredientes concretos de la búsqueda, para descartar recetas inapropiadas para mi consumo.
* **Criterios de aceptación:**
  1. Dado que se consultan recetas, cuando la persona selecciona el ingrediente "cacahuete" en la opción de exclusión, entonces el sistema muestra las recetas que no contienen dicho ingrediente.
  2. Dado que la exclusión puede usarse de forma independiente, cuando la persona selecciona únicamente excluir "gluten" sin ningún otro criterio adicional, entonces el sistema devuelve todas las recetas aptas que no lo contienen.
  3. Dado que existen reglas de validación de filtros, cuando la persona selecciona el mismo ingrediente ("tomate") tanto en la lista de inclusión obligatoria como en la de exclusión, entonces el sistema detecta el conflicto y solicita corregir los filtros antes de mostrar resultados.

#### Revisión INVEST (US-03):
* **Independiente:** Sí. Funciona de manera autónoma o combinada con las historias anteriores.
* **Negociable:** Sí. Permite discutir el diseño visual de los selectores de exclusión.
* **Valiosa:** Sí. Protege la salud del usuario evitando alérgenos e ingredientes no deseados.
* **Estimable:** Sí. Alcance definido y acotado.
* **Pequeña:** Sí. Se centra en la lógica de exclusión y gestión de conflictos.
* **Comprobable:** Sí. Permite comprobar que los alérgenos o ingredientes excluidos no aparecen en los resultados.

---

## 3. Tabla de revisión INVEST

| Criterio INVEST | US-01 | US-02 | US-03 | ¿Cumplen las tres historias? | Justificación / Observaciones |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Independiente** | Aplicado | Aplicado | Aplicado | **Sí** | Cada historia ofrece valor funcional autónomo, compartiendo únicamente la infraestructura base del sistema. |
| **Negociable** | Aplicado | Aplicado | Aplicado | **Sí** | El nivel de abstracción deja margen para definir detalles de interfaz y diseño técnico en el sprint. |
| **Valiosa** | Aplicado | Aplicado | Aplicado | **Sí** | Cada una aporta un beneficio directo y claro para el usuario final (texto, aprovechamiento y seguridad/restricciones). |
| **Estimable** | Aplicado | Aplicado | Aplicado | **Sí** | El alcance y los datos necesarios están perfectamente acotados en los criterios y acuerdos. |
| **Pequeña** | Aplicado | Aplicado | Aplicado | **Sí** | Se centran en una única capacidad manejable sin fragmentarse en tareas técnicas o de diseño. |
| **Comprobable** | Aplicado | Aplicado | Aplicado | **Sí** | Cuentan con criterios de aceptación basados en entradas concretas y resultados observables inequívocos. |
