![C:\\Users\\EPIS\\Documents\\upt.png][image1]

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

Curso:BASE DE DATOS II

Docente:   
Mag. Patrick Cuadros Quiroga

Integrantes:

***Flores Navarro, Eduardo Gino                    (2023076793)***  
***Choqueña, Mauricio Adrian			(2023076799)***

**Tacna – Perú**  
***2026***

 **Proyecto Enmascarado de datos**

# 

# **Versión *3.0***

| CONTROL DE VERSIONES |  |  |  |  |  |
| :---: | :---: | :---: | :---: | :---: | ----- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1.0 | MPV | ELV | ARV | 10/10/2020 | Versión Original |

**ÍNDICE GENERAL**

**[Descripción del Proyecto	3](#descripción-del-proyecto)**

[**Riesgos	3**](#riesgos)

[**Análisis de la Situación Actual	3**](#análisis-de-la-situación-actual)

[**Estudio de Factibilidad	4**](#estudio-de-factibilidad)

[Factibilidad Técnica	4](#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-\(mínimo\),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.)

[Factibilidad Económica	4](#4.2.factibilidad-económica)

[Factibilidad Operativa	4](#4.3.factibilidad-operativa)

[Factibilidad  Legal	4](#4.4.factibilidad-legal)

[Factibilidad  Social	4](#4.5.factibilidad-social)

[Factibilidad  Ambiental	4](#4.6.factibilidad-ambiental)

[**Análisis Financiero	4**](#análisis-financiero)

[**Conclusiones	4**](#conclusiones)

**Informe de Factibilidad**

1. # [**Descripción del Proyecto**](#heading=h.thzj8jtb1l5y) {#descripción-del-proyecto}

**1.1. Nombre del proyecto**

Sistema de Enmascaramiento y Control de Acceso a Datos Sensibles. (Puedes ajustarlo si ya tienen un nombre oficial para la aplicación)

**1.2. Duración del proyecto**

16 semanas. (Puse 16 semanas asumiendo que es lo que dura el semestre académico. Cámbialo a meses o semanas exactas según lo que les haya indicado el profesor).

**1.3. Descripción**

El presente proyecto consiste en el desarrollo de una aplicación orientada al enmascaramiento de datos sensibles en bases de datos, con el objetivo de mejorar la seguridad y el control de acceso a la información. La solución permitirá que los usuarios visualicen únicamente los datos que les corresponden según su rol o área, aplicando técnicas como seguridad a nivel de fila, enmascaramiento dinámico y auditoría de accesos.

La aplicación contará con una arquitectura que integra base de datos, backend y frontend, permitiendo gestionar consultas seguras y monitorear el uso de la información. Además, se incluirán mecanismos de optimización y pruebas de seguridad para garantizar un rendimiento adecuado y prevenir fugas de datos.

**1.4. Objetivos**

**1.4.1 Objetivo general**

Desarrollar una aplicación integral de seguridad en bases de datos que aplique técnicas de enmascaramiento dinámico y seguridad a nivel de fila, con el fin de proteger la información sensible y garantizar que el acceso a los datos esté estrictamente controlado según los roles de los usuarios.

**1.4.2 Objetivos Específicos**

Implementar políticas de seguridad a nivel de fila (RLS): Lograr que la base de datos filtre automáticamente los registros devueltos en las consultas basándose en el rol o área del usuario que realiza la petición.

Desarrollar un módulo de enmascaramiento dinámico: Lograr ocultar parcial o totalmente los campos confidenciales (como contraseñas, correos o datos financieros) para aquellos usuarios que no tengan los privilegios necesarios.

Construir una arquitectura web completa (Frontend y Backend): Lograr una interfaz intuitiva que permita a los administradores gestionar los roles y a los usuarios realizar consultas seguras sobre la base de datos.

Integrar mecanismos de auditoría: Lograr un registro automatizado (mediante triggers o logs en el backend) de los accesos y consultas realizadas sobre los datos sensibles para facilitar el monitoreo ante posibles incidentes.

2. # **Riesgos** {#riesgos}

Se han identificado los siguientes riesgos que podrían afectar el éxito del proyecto:

* **Riesgo Tecnológico:** Incompatibilidad entre las funciones de enmascarado dinámico de la base de datos seleccionada y el framework del backend.  
* **Riesgo de Seguridad:** Configuración inadecuada de las políticas de Seguridad a Nivel de Fila (RLS), lo que podría permitir filtraciones de datos no autorizadas durante las pruebas.  
* **Riesgo de Gestión:** Retrasos en el cronograma de desarrollo debido a la complejidad de integrar múltiples capas de seguridad (Base de datos \+ API).

3. # **Análisis de la Situación Actual** {#análisis-de-la-situación-actual}

**3.1. Planteamiento del problema** Actualmente, muchas organizaciones enfrentan el desafío de gestionar bases de datos donde usuarios de distintos niveles (desarrolladores, analistas, administrativos) acceden a la información sin un control granular. La situación actual se caracteriza por:

* **Exposición innecesaria:** Usuarios con privilegios básicos pueden visualizar datos sensibles (DNI, correos, saldos) que no son requeridos para sus funciones.  
* **Falta de segregación:** No existe una distinción automática de registros; todos los usuarios ven la misma cantidad de filas a menos que se programen filtros manuales complejos en cada aplicación.  
* **Vulnerabilidad:** La ausencia de técnicas de enmascarado aumenta el riesgo de fuga de información por parte de personal interno o accesos no autorizados.

**3.2. Consideraciones de hardware y software** Para la resolución de esta problemática, se han evaluado las siguientes tecnologías disponibles en el entorno actual de desarrollo:

* **Hardware:** Se cuenta con estaciones de trabajo con procesadores de arquitectura x64 y un mínimo de 8GB de RAM para soportar entornos de contenedores o servidores locales de bases de datos.  
* **Software Actual:** Se dispone de sistemas de gestión de bases de datos relacionales (como PostgreSQL o SQL Server) que ya integran de forma nativa funcionalidades de RLS y enmascarado, las cuales serán aprovechadas para el proyecto.  
* **Tecnología de Aplicación:** Se utilizarán entornos de ejecución como Node.js o Python, que permiten una integración fluida con los protocolos de seguridad de la base de datos.

4. # **Estudio de Factibilidad** {#estudio-de-factibilidad}

## El presente estudio de factibilidad evalúa la viabilidad técnica, económica, operativa, legal, social y ambiental para la implementación del sistema de enmascarado. Las actividades de evaluación incluyeron el análisis de compatibilidad de motores de base de datos y la estimación de recursos de hardware, contando con la revisión y aprobación de los responsables del proyecto. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

#### **4.1. Factibilidad Técnica**

## Se ha determinado que el proyecto es técnicamente viable, ya que se cuenta con el conocimiento y los recursos tecnológicos necesarios para su ejecución. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

* ## **Evaluación de Tecnología Actual:** Se utilizará el sistema de gestión de bases de datos PostgreSQL (versión 15 o superior), seleccionado por su robustez en la implementación nativa de *Row Level Security* (RLS) y su capacidad para manejar funciones de enmascaramiento dinámico mediante extensiones o disparadores (*triggers*). {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

* ## **Software de Desarrollo:** {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

  * ## **Backend:** Se empleará Node.js con Express, debido a su eficiencia en el manejo de peticiones asíncronas y la existencia de librerías maduras para la gestión de políticas de seguridad en la conexión. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

  * ## **Frontend:** Se utilizará React.js para construir una interfaz administrativa que permita la gestión de roles de manera dinámica. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

  * ## **Sistemas Operativos:** El desarrollo y despliegue se realizá sobre el entorno Windows con soporte para Docker, facilitando la portabilidad del sistema. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

* ## **Hardware (Infraestructura):** {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

  * ## **Servidor de Desarrollo:** Estación de trabajo con procesador de 4 núcleos (mínimo), 16GB de memoria RAM y 500GB de almacenamiento SSD para garantizar la fluidez en el procesamiento de grandes volúmenes de datos durante las pruebas de enmascaramiento. {#servidor-de-desarrollo:-estación-de-trabajo-con-procesador-de-4-núcleos-(mínimo),-16gb-de-memoria-ram-y-500gb-de-almacenamiento-ssd-para-garantizar-la-fluidez-en-el-procesamiento-de-grandes-volúmenes-de-datos-durante-las-pruebas-de-enmascaramiento.}

  * ## **Red:** Se requiere una infraestructura de red física con acceso a internet para la gestión de dependencias y despliegue en entornos locales controlados.

## 	**4.2.Factibilidad Económica** {#4.2.factibilidad-económica}

El propósito de este estudio es determinar los beneficios económicos del sistema propuesto en contraposición con los costos de implementación. Se ha evaluado que la institución cuenta con la infraestructura básica, pero el proyecto requiere una inversión en horas de desarrollo y materiales de oficina.

**4.2.1. Costos Generales** Gastos en accesorios y material de oficina necesarios para los procesos diarios de documentación y planificación.

| Descripción | Cantidad | Costo Unitario (S/) | Total (S/) |
| :---: | :---: | :---: | :---: |
| Resmas de papel Bond A4 | 2 | 15.00 | 30.00 |
| Lapiceros y marcadores | 1 kit | 20.00 | 20.00 |
| Folderes y archivadores | 5 | 5.00 | 25.00 |
| **Total Costos Generales** |  |  | **75.00** |

**4.2.2. Costos operativos durante el desarrollo** Costos estimados para la operatividad de las actividades durante las 16 semanas de desarrollo (aprox. 3 meses).

| Servicio | Meses | Costo Mensual (S/) | Total (S/) |
| :---- | :---- | :---- | :---- |
| Energía Eléctrica | 4 | 50.00 | 200.00 |
| Internet de alta velocidad | 4 | 100.00 | 400.00 |
| Agua y servicios básicos | 4 | 30.00 | 120.00 |
| **Total Costos Operativos** |  |  | **720.00** |

**4.2.3. Costos del ambiente** Requerimientos técnicos para la implantación y pruebas del software.

| Descripción | Cantidad | Costo (S/) |
| :---- | :---- | :---- |
| Servicio de Hosting / Servidor Cloud (Pruebas) | 4 meses | 150.00 |
| Dominio .com / .pe | 1 año | 60.00 |
| Certificado SSL de seguridad | 1 año | 0.00 (Let's Encrypt) |
| **Total Costos de Ambiente** |  | **210.00** |

#### **4.2.5. Costos totales del desarrollo del sistema**

Este cuadro resume la inversión mínima necesaria para garantizar la viabilidad del software.

| Categoría | Total (S/) |
| :---: | :---: |
| Costos Generales (Materiales) | 75.00 |
| Costos Operativos (Servicios) | 720.00 |
| Costos del Ambiente (Hosting/Dominio) | 210.00 |

## 	**4.3.Factibilidad Operativa** {#4.3.factibilidad-operativa}

	La aplicación estará diseñada con una interfaz sencilla e intuitiva, permitiendo a los 	usuarios acceder al sistema mediante un proceso de autenticación y visualizar la 		información según sus permisos. Esto facilita su uso incluso para personas con 		conocimientos básicos en sistemas.

	Asimismo, el sistema automatizará el control de acceso a los datos mediante roles 		y políticas de seguridad, reduciendo la necesidad de intervención manual y 		minimizando errores humanos.

	Nuestro equipo cuenta con toda la capacidad de gestionar e implementar 		el sistema dentro del entorno del curso, siguiendo una estructura organizada 		basada en módulos.

## 	**4.4.Factibilidad  Legal** {#4.4.factibilidad-legal}

	El proyecto es legalmente viable, ya que no infringe ninguna normativa vigente y 		promueve el uso adecuado de la información.

	La aplicación está orientada a la protección de datos sensibles mediante técnicas 		como el enmascaramiento de datos y el control de acceso, lo cual está alineado 		con principios de seguridad y confidencialidad de la información.

	Asimismo, el desarrollo del proyecto se realiza con fines académicos, utilizando 		herramientas legales y evitando el uso de software no autorizado. No se 		contempla el uso indebido de datos reales, ya que se trabajará con información 		 simulada o controlada dentro del entorno del curso.

## 	**4.5.Factibilidad  Social** {#4.5.factibilidad-social}

	La implementación de mecanismos como el enmascaramiento de datos y el 		control de acceso ayuda a prevenir el uso indebido de la información, 		promoviendo la privacidad y la confianza en los sistemas informáticos.

	Asimismo, el sistema no genera un impacto negativo en los usuarios, ya que está 		diseñado para ser fácil de usar y no altera significativamente sus actividades 		dentro de la aplicación.

## 	**4.6.Factibilidad  Ambiental** {#4.6.factibilidad-ambiental}

	Al tratarse de una aplicación informática, no requiere el uso de recursos físicos 		contaminantes ni procesos industriales. Asimismo, su ejecución se realiza en 		equipos de cómputo convencionales, lo que implica un consumo energético 		reducido.

5. # **Análisis Financiero** {#análisis-financiero}

	El análisis financiero del proyecto indica que no se requiere una inversión 		significativa para su desarrollo, ya que se utilizarán herramientas de software 		accesibles y, en su mayoría, gratuitas o con licencias académicas.

	Los principales recursos necesarios son:

* **Equipos de cómputo**, los cuales ya están disponibles para los integrantes del equipo.  
* **Software de desarrollo y gestión de bases de datos**, como motores de base de datos y entornos de programación.  
* **Tiempo de desarrollo**, considerado como el principal recurso invertido en el proyecto.

	No se contemplan costos adicionales relacionados con infraestructura, licencias 		comerciales o contratación de personal externo.

	En un contexto real, la implementación de este tipo de sistema podría generar 		beneficios económicos indirectos, como la reducción de riesgos asociados a la fuga 	de datos, evitando posibles pérdidas financieras o sanciones.

6. # **Conclusiones** {#conclusiones}

   A partir del análisis realizado, se concluye que el proyecto de desarrollo de una aplicación de enmascaramiento de datos es viable en sus diferentes dimensiones.

   Desde el punto de vista técnico, se cuenta con las herramientas y conocimientos necesarios para su implementación. En el aspecto económico, no se requieren grandes inversiones, lo que facilita su desarrollo en un entorno académico.

   Como también, el proyecto es operativamente viable, ya que puede ser utilizado sin dificultades por los usuarios, y cumple con criterios legales y sociales al promover la protección de la información sensible.

   Adicionalmente, no presenta impactos negativos en el ámbito ambiental, lo que refuerza su viabilidad integral.

   En conclusión, el proyecto puede desarrollarse de manera adecuada y representa una solución relevante para mejorar la seguridad en el manejo de datos, estando sujeto a mejoras conforme avance su implementación.

[image1]: <data:image/png;base64,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>