# Orthogonal Defect Classification (clasificación de defectos ortogonales)


* ODC es un marco sistemático para la clasificación de defectos de software desarrollado por IBM a principios de los años 1990.
* ODC es un concepto que permite la retroalimentación durante el proceso a los desarrolladores mediante la extracción de firmas en el proceso de desarrollo a partir de defectos.
* ODC utiliza información semántica de los defectos para extraer relaciones causa-efecto en el proceso de desarrollo.
* ODC tiene mecanismos integrados para el escape de fase y el análisis de causa raíz.
* ODC se conoce como "MRI" en un defecto de software.

ODC v5.2 para diseño y código:

Durante el desarrollo de un software en curso, la información sobre defectos está disponible en dos momentos específicos. Cuando se abre un registro de defectos, normalmente se conocen las circunstancias que llevaron al descubrimiento del defecto y el probable impacto para el usuario. Tres atributos capturados en este momento son:

* Actividad ODC: Revisión de diseño, Prueba unitaria, Prueba de función, etc.
* Activador ODC: el entorno o la condición que provocó la exposición de los defectos, normalmente capturado en escenarios recreados.
* Impacto ODC: El impacto potencial del defecto en el usuario previsto.

Cuando el registro de defectos se cierra después de aplicar la corrección, se conocen la naturaleza exacta del defecto y el alcance de la corrección. Cinco atributos capturados al momento del cierre son:

* Objetivo ODC: representa el artefacto de alto nivel que se solucionó. Cuando hay un defecto en la implementación del código en relación con el Diseño o los Requisitos, los desarrolladores corrigen el código y, por lo tanto, el "Código" será el objetivo adecuado. En los casos en que la implementación del código sea diferente de las especificaciones en Diseño o Requisitos, si la implementación del código se acepta en lugar del Diseño o Requisitos, implícitamente esos documentos deberán cambiarse y, por lo tanto, se elegirá "Diseño" o "Requisitos" como objetivo. En las prácticas de desarrollo de software comercial, ese rigor no es común.
* Tipo de defecto ODC: el alcance de la solución (asignación, verificación, algoritmo, etc.)
* Calificador ODC: la solución requirió la adición de algún código faltante o la corrección del código incorrecto existente o la eliminación de código superfluo.
* ODC Source captura el origen del código que tenía el defecto (desarrollado internamente, reutilizado de una biblioteca, etc.)
* Antigüedad ODC: Indica la antigüedad del código que tuvo el defecto en términos de su historial de desarrollo (Código base de una versión anterior, Código nuevo para la versión actual, etc.),

Estos ocho atributos de defecto, en conjunto, capturan la semántica de un defecto desde todas las perspectivas relevantes. El documento ODC para Diseño y Código brinda detalles relacionados con el esquema ODC original, los pasos reales involucrados en la clasificación de defectos y recomendaciones para la implementación del proceso de recolección de defectos.

# Referencias
- Software Quality Exp. (2018, 21 marzo). What is Orthogonal Defect Classification (ODC)? By Vivek Vasudeva. Medium. https://medium.com/@SWQuality3/what-is-orthogonal-defect-classification-odc-by-vivek-vasudeva-f2e49917f478
- Orthogonal Defect Classification (Archival) - IBM. (s. f.). https://researcher.watson.ibm.com/researcher/view_group_subpage.php?id=5020

