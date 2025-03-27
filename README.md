# TESIS_MAESTRIA

## **Desarrollo de la exposición técnica de analítica de datos que se generó en el proyecto de posgrado denominado "Diseño de un sistema de prevención del síndrome de túnel carpiano implementando redes neuronales artficiales"**. 

### **Se comparte el enlace del documento que se encuentra alojado en el RIUD, para los lectores que quieran explorar todo el proceso formulado: [Tesis de Maestría](https://repository.udistrital.edu.co/items/34589746-cb5e-4336-9f70-668bf60ea23b)**


El síndrome del túnel carpiano (STC) es una enfermedad que se presenta cuando existe una presión considerable en el nervio mediano en la zona que pasa por la muñeca, donde se generan dolores, debilimtamiento muscular, hormigueo, conocido como parestesias, adicionalmente de una disminución considerable del movimiento de la mano en la zona tenar, afectando principalmente el agarre del dedo pulgar. El STC es considerado desde el 2003 una enfermedad profesional por la Unión Europea y es visualizada a nivel global como una de las enfermedades osteomusculares más frecuentes, debido al alto desgaste y la limitación significativa que genera en las manos de  quienes sufren este mal, otro punto adicional de esta área es que el STC aparece generalmente por la mala postura que las personas generan en sus manos, ya que al posicionarlas de forma incorrecta, generan un desgaste continuo de la muñeca y con ello una presión en el nervio mediano que finalmente genera los dolores fuertes que es cuando las personas van a consultar y ya no quedan opciones de prevención, sino solo de mitigación que en algunos casos no son efectivos y requieren de cirugías qcon posibilidad alta de limitar significativamente los movimientos de las manos. En el proyecto desarrollado se buscó generar un sistema cómodo que permitiera una prevención temprana del síndrome de túnel del carpo. Teniendo presente lo anterior se procedió a generar diferentes etapas del proyecto, como se muestra en la siguiente figura:

![image](https://github.com/user-attachments/assets/ae64cd7c-83da-4094-8fc0-b3e25ac658b5)

De forma breve se expone el diseño, el desarrollo y la implementación de cada uno de los módulos, comenzando con:
## Arquitectura Global Módulo de Medición 

Se desarrolló la siguiente arquitectura para detallar de forma directa y con una información detallada el comportamiento del nervio mediando específicamente entre la muñeca y la mano teniendo:

![MEDICION](https://github.com/user-attachments/assets/601a66ee-59b1-4b53-adb2-a08946b5d95f)

De esta arquitectura global se tuvo presente las siguientes arquitecturas para cada módulo de medición:

### Arquitectura del módulo de Agarre con Sensores Velostat

La arquitectura diseñada para el sistema de medición por medio del velostat con los diferentes sensores son:

![ARQUI1](https://github.com/user-attachments/assets/361ccb95-2d5c-4410-a086-1b6830d34d25)

Donde cada sensor en cada uno de los diferentes elementos se caracterizó como se expone en el siguiente diagrama:

![ARQUI2](https://github.com/user-attachments/assets/99508507-f82c-4db3-8dce-d01c48bcbeef)

### Arquitectura de la Pulsera Electromiográfica

La arquitectura diseñada para la pulsera electromiográfica es:

![PULSERA](https://github.com/user-attachments/assets/cdcc23e7-cf1f-4587-adaa-1b3eb543135d)

Teniendo como resultado final:

![PROTOPULSER](https://github.com/user-attachments/assets/9da7cdde-a9ba-4509-96e7-d46d246852c5)

### Estructura de la Encuesta Generada a los Usuarios

Se tuvo presente lo siguiente parav el desarrollo de la encuesta:

![ARQUI3](https://github.com/user-attachments/assets/eebef870-fa06-4405-ba83-4fcbec45e108)

### Estructura de la Aplicación Móvil

Se desarrolló la aplaicación por medio del aplicativo MIT App Inventor, teniendo presente lo siguiente:

![ARQUI4](https://github.com/user-attachments/assets/15425ad8-0f64-4621-b125-99693b95b3c0)

Posteriormente se procedió a desarrollar las diferentes capturas de datos teniendo presente, los datos obtenidos de los sensores desarrollados con velostat:

![image](https://github.com/user-attachments/assets/5f6d9f01-387f-49b3-826a-103557723ab4)

Y luego a graficarlos para entender el comportamiento que tenía cada sensor, como es el caso de los datos que capturó el sensor 1 (para visualizar todos los resultados revisar [Tesis de Maestría](https://repository.udistrital.edu.co/items/34589746-cb5e-4336-9f70-668bf60ea23b) )

![RESULT_SEN1](https://github.com/user-attachments/assets/148d3ff1-ba04-4bba-9109-4c9522202303)

Luego se visualizó los datos capturados con el sensor electromiográfico teniendo:

![RESULT_EMG](https://github.com/user-attachments/assets/2c4fb93a-304e-4cb2-9fd0-136ae5960c0d)

Y posteriormente los resultados de la encuesta. Luego se unificó los datos y se generó una extracción de todos los valores máximos, mínimos, medias, modas y medianas para la generación de la base de datos teniendo:

![BASEDATOS](https://github.com/user-attachments/assets/358dfe7a-8e8c-40c6-ba00-0dec956d8eda)

Posteriormente se desarrolló una visualización por medio de pairplot para observar si los datos tenían una distribución normal, por medio del siguiente código:

´´´python
#Desarrollo de Gr´aficos Por Pares
sns.pairplot(modSANT)
#Desarrollo de Gr´aficos por Densidad
sns.pairplot(modSANT, diag_kind = "kde")
´´´


















