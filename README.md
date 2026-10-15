# 👶 Sistema de Gestión de Matrículas — Jardín Infantil

## 📋 Descripción del proyecto

Se requiere desarrollar una aplicación de escritorio en **Java**, utilizando el IDE **NetBeans** y componentes gráficos **Java Swing (JFrame)**, para administrar la información de los niños matriculados en un jardín infantil.

El jardín ofrece dos grados académicos:

- **Prejardín**
- **Jardín**

La aplicación debe permitir registrar, consultar y eliminar estudiantes, almacenar la información en archivos de texto y generar reportes estadísticos sobre los niños matriculados.

Como requisito de implementación, se debe utilizar una **lista circular simplemente enlazada** para gestionar los registros de los estudiantes.

## 🎯 Objetivo general

Desarrollar un sistema de gestión de estudiantes que permita administrar la información de los niños matriculados en los grados de Prejardín y Jardín, utilizando estructuras de datos dinámicas, archivos de texto y una interfaz gráfica de usuario.

## 🧰 Tecnologías y herramientas

| Tecnología o herramienta | Uso |
|---|---|
| Java | Lenguaje de programación |
| NetBeans | Entorno de desarrollo |
| Java Swing | Desarrollo de la interfaz gráfica |
| JFrame | Ventana principal de la aplicación |
| JTable | Visualización de los registros de estudiantes |
| Lista circular simplemente enlazada | Estructura de datos para gestionar los estudiantes |
| Archivos de texto (`.txt`) | Almacenamiento persistente de la información |
| UML | Diseño y documentación de las clases del sistema |

## 👧👦 Información de los estudiantes

Cada estudiante debe tener los siguientes datos:

| Campo | Descripción | Restricción |
|---|---|---|
| Identificación | Documento o número de identificación del estudiante | No se puede repetir |
| Nombre completo | Nombres y apellidos del estudiante | Obligatorio |
| Sexo | Sexo del estudiante | Debe permitir identificar niñas y niños |
| Edad | Edad del estudiante en años | Debe estar entre 4 y 7 años |
| Grado | Grado en el que está matriculado | Prejardín o Jardín |

> **Nota:** Aunque la descripción inicial menciona la identificación, el nombre completo y el sexo como datos básicos, también es necesario registrar la edad y el grado para validar las matrículas y generar los reportes solicitados.

## ⚙️ Requerimientos funcionales

### 1. Registrar estudiantes

La aplicación debe permitir ingresar la información de un nuevo estudiante.

Al registrar un estudiante, el sistema debe:

- Solicitar su identificación, nombre completo, sexo, edad y grado.
- Validar que los campos obligatorios estén completos.
- Verificar que la edad esté entre 4 y 7 años.
- Permitir únicamente los grados Prejardín y Jardín.
- Comprobar que la identificación no esté registrada previamente.
- Incorporar el estudiante a la lista circular simplemente enlazada.
- Guardar la información en un archivo de texto para conservarla después de cerrar la aplicación.

### 2. Consultar estudiantes

El sistema debe permitir buscar un estudiante por medio de su número de identificación.

La búsqueda debe:

- Solicitar la identificación del estudiante.
- Consultar los registros almacenados en el archivo de texto.
- Mostrar los datos del estudiante si existe.
- Informar al usuario cuando no se encuentre ningún registro con esa identificación.

### 3. Eliminar estudiantes

La aplicación debe permitir eliminar un estudiante utilizando su identificación.

Para realizar esta operación se debe utilizar un archivo temporal o auxiliar.

El procedimiento será el siguiente:

1. Solicitar la identificación del estudiante que se desea eliminar.
2. Leer los registros del archivo principal.
3. Copiar al archivo temporal todos los registros, excepto el del estudiante seleccionado.
4. Verificar si el estudiante fue encontrado.
5. Si existe, reemplazar el archivo original por el archivo temporal actualizado.
6. Actualizar la lista circular simplemente enlazada para mantener sincronizados los datos en memoria y en el archivo.
7. Informar al usuario si la eliminación se realizó correctamente o si el estudiante no existe.

> **Importante:** Si el estudiante no existe, el sistema no debe eliminar ni modificar los demás registros.

## 📊 Requerimientos de reportes

El sistema debe contar con un menú de opciones para consultar y generar los siguientes informes.

### Reporte 1. Cantidad de estudiantes por grado y sexo

Mostrar la cantidad de niñas y niños matriculados en cada grado, así como el total de estudiantes por grado.

| Grado | Niñas | Niños | Total |
|---|---:|---:|---:|
| Prejardín | Cantidad | Cantidad | Total |
| Jardín | Cantidad | Cantidad | Total |
| **Total general** | **Cantidad** | **Cantidad** | **Total** |

Los valores deben calcularse a partir de los registros almacenados.

### Reporte 2. Listado de estudiantes de Prejardín

Mostrar los nombres completos de todos los estudiantes matriculados en el grado Prejardín.

El listado debe generarse utilizando la información almacenada en el sistema.

### Reporte 3. Listado de estudiantes de Jardín

Mostrar los nombres completos de todos los estudiantes matriculados en el grado Jardín.

El listado debe generarse utilizando la información almacenada en el sistema.

### Reporte 4. Promedio de edad por sexo

Calcular el promedio de edad de las niñas y el promedio de edad de los niños de todo el jardín infantil, sin separar por grado.

Las fórmulas son:

**Promedio de edad de las niñas**

\[
\text{Promedio} =
\frac{\text{Suma de las edades de las niñas}}
{\text{Cantidad de niñas}}
\]

**Promedio de edad de los niños**

\[
\text{Promedio} =
\frac{\text{Suma de las edades de los niños}}
{\text{Cantidad de niños}}
\]

Si no hay estudiantes de alguno de los grupos, el sistema debe informar que no es posible calcular ese promedio.

## 🗂️ Requerimientos de almacenamiento

La información de los estudiantes debe guardarse en uno o varios archivos de texto plano.

El sistema debe garantizar que:

- Los registros se conserven después de cerrar la aplicación.
- Los datos puedan recuperarse al iniciar nuevamente el programa.
- No se registren identificaciones duplicadas.
- Las operaciones de registro y eliminación actualicen correctamente el archivo.
- La eliminación de un estudiante se realice mediante un archivo temporal o auxiliar.

Se puede utilizar un archivo como `estudiantes.txt` para almacenar los registros.

**Ejemplo ilustrativo del contenido del archivo:**

```text
1001;María Fernanda López;Femenino;5;Prejardín
1002;Juan David Pérez;Masculino;6;Jardín
1003;Laura Sofía Díaz;Femenino;4;Prejardín
```

El formato anterior es una propuesta de organización de los datos. Se puede utilizar otro formato de texto plano siempre que permita guardar y recuperar correctamente la información.

## 🔗 Estructura de datos obligatoria

Se debe implementar una **lista circular simplemente enlazada**.

Esta estructura debe utilizarse para gestionar los estudiantes durante la ejecución del programa.

La lista debe permitir:

- Insertar nuevos estudiantes.
- Recorrer los registros.
- Buscar estudiantes por identificación.
- Eliminar estudiantes de la estructura.
- Obtener los datos necesarios para generar los reportes.

En una lista circular simplemente enlazada, el último nodo apunta nuevamente al primer nodo. Cada nodo contiene la información de un estudiante y una referencia al siguiente nodo.

La estructura debe estar implementada en el código del proyecto; no basta con utilizar una colección estándar de Java en su lugar.

## 🖥️ Interfaz gráfica

La aplicación debe contar con una interfaz gráfica desarrollada con Java Swing.

Se recomienda implementar una ventana principal con un menú de opciones y formularios para administrar los estudiantes.

### Opciones sugeridas del menú

| Opción | Funcionalidad |
|---|---|
| Registrar estudiante | Ingresar los datos de un nuevo estudiante |
| Consultar estudiante | Buscar por identificación |
| Eliminar estudiante | Eliminar un registro por identificación |
| Listar estudiantes | Mostrar los registros en una tabla |
| Reporte por grado y sexo | Mostrar cantidades de niñas y niños por grado |
| Listado de Prejardín | Mostrar los nombres de los estudiantes de Prejardín |
| Listado de Jardín | Mostrar los nombres de los estudiantes de Jardín |
| Promedio de edades | Calcular los promedios por sexo |
| Salir | Cerrar la aplicación |

### Componentes gráficos recomendados

- `JFrame`: ventana principal.
- `JPanel`: organización de los formularios y secciones.
- `JLabel`: etiquetas de los campos.
- `JTextField`: ingreso de identificación y nombre.
- `JComboBox`: selección del sexo y del grado.
- `JSpinner` o `JTextField`: ingreso de la edad.
- `JButton`: ejecución de las operaciones.
- `JTable`: visualización de los estudiantes.
- `JOptionPane`: mensajes de confirmación, información y error.

Estos componentes son sugeridos para facilitar el desarrollo. Se pueden utilizar otros componentes de Swing si cumplen con los requerimientos.

## 📐 Diagrama de clases UML

El proyecto debe incluir un diagrama de clases UML que represente el diseño de la solución.

El diagrama debe mostrar las clases principales, sus atributos, métodos y relaciones.

Se recomienda contemplar clases como:

- `Estudiante`: representa los datos de cada estudiante.
- `Nodo`: almacena un estudiante y la referencia al siguiente nodo.
- `ListaCircular`: administra las operaciones de la lista circular simplemente enlazada.
- `ArchivoEstudiantes`: gestiona la lectura, escritura y eliminación de registros en los archivos de texto.
- `GestorEstudiantes`: coordina las operaciones de registro, búsqueda, eliminación y generación de reportes.
- `VentanaPrincipal`: contiene la interfaz gráfica de la aplicación.

Los nombres y la distribución de las clases pueden ajustarse según el diseño definitivo de la solución.

### Condiciones del diagrama UML

1. Debe elaborarse manualmente con una herramienta de diagramación UML.
2. **No está permitido utilizar el plugin de NetBeans para generar automáticamente el diagrama de clases.**
3. Se debe entregar una imagen del diagrama.
4. También se debe incluir el archivo fuente del diagrama para poder editarlo.
5. Se debe entregar una versión en PDF del diagrama UML.

## 📦 Entregables

La actividad se debe realizar en parejas, es decir, con dos integrantes.

Todos los archivos necesarios para la entrega deben organizarse y comprimirse en un archivo `.zip`.

La carpeta comprimida debe contener los siguientes elementos:

| N.º | Entregable | Descripción |
|---:|---|---|
| 1 | Proyecto NetBeans | Código fuente y archivos necesarios para abrir y ejecutar la aplicación |
| 2 | Documento Word | Portada institucional con los datos de los integrantes y la información académica solicitada |
| 3 | Diagrama UML en imagen | Representación visual de las clases del sistema |
| 4 | Archivo fuente UML | Archivo editable utilizado para elaborar el diagrama |
| 5 | Diagrama UML en PDF |
