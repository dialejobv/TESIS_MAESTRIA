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

```python
#Desarrollo de Gr´aficos Por Pares
sns.pairplot(modSANT)
#Desarrollo de Gr´aficos por Densidad
sns.pairplot(modSANT, diag_kind = "kde")
```

Teniendo presente el siguiente resultado para el caso de gráficos de distribución y gráficos por densidad para el caso de la pelota anti-estrés (Para explorar todos los resultados dirigirse a la [Tesis de Maestría](https://repository.udistrital.edu.co/items/34589746-cb5e-4336-9f70-668bf60ea23b)) 

![image](https://github.com/user-attachments/assets/d65bbe5d-e7ba-4037-b105-7e5211405258)

Don se visualiza la relación cruzada entre par´ametros de la pelota antiestrés con a) Histogramas y b) Densidades [Fuente Propia].

Posteriormente se desarrolló las correlaciones de todas las variables de todos los códigos teniendo:

```Python
corr_df = corrSPE1.corr(method = ’spearman’)
plt.figure(figsize=(30,20))
sns.heatmap(corr_df, annot = True)
plt.show()
```

Y visualizando lo siguiente en el caso del ejemplo del sensor 1 (para visualizar todos los resultados observar [Tesis de Maestría](https://repository.udistrital.edu.co/items/34589746-cb5e-4336-9f70-668bf60ea23b)):

![CorrSPE1](https://github.com/user-attachments/assets/b1ea6ff9-aeef-4dd9-9286-3c19d6cb2141)

### Red Neuronal

Luego se procedió a usar la nueva base de datos tratada para el desarrollo de una red neuronal artificial teniendo primero la carga de la base de datos:

```Python
stc = pnd.read_excel('BD_COMPLETA_SIN_STC.xlsx',parse_dates=True)
```

En este apartado se expone la visualización de la base de datos:

![image](https://github.com/user-attachments/assets/af6ed7a9-f4c0-40de-9a5c-16134f8a7373)

Posteriormente se desarrolló la normalización con la función MinMaxScaler teniendo el siguiente fragmento de código:

```Python
from sklearn.preprocessing import MinMaxScaler
#Normalización
scaler = MinMaxScaler()

#Procedo a normalizar las variables de entrada anteriores teniendo:
stc_n = scaler.fit_transform(stc)
stcres_n = scaler.fit_transform(stcres)
```

Luego se desarrolla una validación de entradas y salidas en la red:

```Python
# Filtro de valores no nulos por medio de la función dropna
stc_n = stc_n.dropna()
stcres_nfinal = stcresana_n.dropna()

#Desarrollo de la ventana 80% entrenamiento y 20% validacion
size = int(len(stc_n) * 0.80)
size2 = int(len(stcres_n) * 0.80)

#Validación de las entradas y salidas de la red
Xtrain, Xtest = stc_n[0:size], stc_n[size:len(stc_n)] 
Ytrain, Ytest = stcres_nfinal[0:size2], stcres_nfinal[size2:len(stcres_n)]
```

Posteriormente se desarrolló una arquitectura de red neuronal, teniend``o presente la salida como pacientes con posibilidad de síndrome de túnel del carpo y pacientes sanos, se expone el siguiente código:

```Python
# Se explora la tasa de aprendizaje 

lr = 0.01         # learning rate
nn = [94, 94, 1]  # número de neuronas por capa.

#Definición de las tres capas que componen la red neuronal a desarrollar
#capaEntrada = tf.keras.layers.Dense(units=95,input_shape=[95])
#capaOculta =  tf.keras.layers.Dense(units=95, activation='relu'))
#capaSalida =  tf.keras.layers.Dense(units=1, activation='sigmoid'))

# secuencia de capas.
model = kr.Sequential()

# Añadimos la capa 1-Las neuronas que adquieren los datos de entrada
#capaEntrada = model.add(kr.layers.Dense(nn[1], activation='relu'))

# Añadimos la capa 2-Las nueronas de la capa Oculta
capaOculta = model.add(kr.layers.Dense(nn[1], activation='relu'))

# Añadimos la capa 3-La neurona de Salida
capaSalida = model.add(kr.layers.Dense(nn[2], activation='sigmoid'))

#Desarrollo del modelo
#modelo = tf.keras.Sequential([capaEntrada,capaOculta,capaSalida])

# Se compila el modelo, definiendo la función de coste y el optimizador.
model.compile(
    optimizer=tf.keras.optimizers.Adam(lr),
    loss = 'mean_squared_error',
    metrics=['binary_accuracy']
)

# Y entrenamos al modelo. Los callbacks 
print('En esta parte se inicia el entrenamiento de la ANN')
historial = model.fit(stc_n,stcres_nfinal, epochs=1000)#, verbose=False)
print('Modelo Entrenado')

# Se evalua el modelo
scores = model.evaluate(stc_n, stcres_nfinal)
print("\n%s: %.2f%%" % (model.metrics_names[1], scores[1]*100))

#Se realiza las  predicciones posibles, pasando las entradas:
print (model.predict(Xtest).round())
```

Teniendo presente el siguiente resultado cuando se probó:

![image](https://github.com/user-attachments/assets/b6532371-b1a9-48c0-80bc-f155161d6d32)

Sin embargo se visualizó un alto porcentaje de error por lo que la red no se acopló muy bien a los diferentes datos, por lo que se cambió la visualización para que fuera más flexible teniendo presente la variable RES que permite una adaptabilidad del sistema para una mejor respuesta teniendo:

```Python
import tensorflow as tf
import tensorflow.keras as kr

# Se explora la tasa de aprendizaje y el número de neuronas por capa
lr = 0.01         # learning rate
nn = [95, 95,8, 1]  # número de neuronas por capa.

# Creamos el objeto que contendrá a nuestra red neuronal, como
# secuencia de capas.
model = kr.Sequential()

# Añadimos la capa 1-Las neuronas que adquieren los datos de entrada
capaEntrada = model.add(kr.layers.Dense(nn[1], activation='relu'))

# Añadimos la capa 2-Las nueronas de la capa Oculta
capaOculta = model.add(kr.layers.Dense(nn[2], activation='relu'))

# Añadimos la capa 3-La neurona de Salida
capaSalida = model.add(kr.layers.Dense(nn[3], activation='sigmoid'))

# Compilamos el modelo, definiendo la función de coste y el optimizador.
model.compile(loss='mse', optimizer=kr.optimizers.Adam(lr), metrics=['binary_accuracy'])

# Y entrenamos al modelo. Los callbacks 
model.fit(stc,stcdiag, epochs=100)
```
Teniendo presente el siguiente comportamiento de las siguientes comparaciones:

![image](https://github.com/user-attachments/assets/9c4083f3-47b6-43b4-b067-ef2011784628)

Posteriormente se visualizó la gráfica de magnitud de pérdida teniendo:

![image](https://github.com/user-attachments/assets/127bafda-d82c-43bd-9f75-a7be6c061fdc)

Finalmente se generó el almacenamiento de lá red en h5 y se procedió a generar un componente de visualizaicón por medio del microframework de flask para desarrollar una interfaz sencilla con su respectiva integración teniendo:

![image](https://github.com/user-attachments/assets/a8bd47da-07ab-4cf2-be39-9967d96b31ef)

Finalmente la arquitectura completa quedó así:

![image](https://github.com/user-attachments/assets/00dab6f2-3379-405e-b8b3-39dd92c5840b)


## Conclusiones

1. Se observó que en la construcción de los diferentes dispositivos para el kit de
presión fue fundamental que los elementos de agarre fueran de un material
plástico resistente, para que pudieran soportar las presiones de los diferentes
agarres realizados por los usuarios, además fue importante recubrir los
diferentes sensores de presión usados en cada uno de los diferentes agarres
con papel contact transparente para una mayor duración, anexo a lo anterior se
usó tres capas de velostat con cable de fibra multifilar como se mostró en el
capítulo de caracterización con el objetivo de tener una ventana más grande en
la medición cuando el usuario fuera desarrollar el agarre.

2. Se observó una variación significativa en los sensores de velostat al momento
de desarrollar validaciones consecutivas, dado que es un material bastante
sensible a la presión, que en este caso se dio por la fuerza de agarre del
material, por lo que en mediciones múltiples, se dejaba en estado de reposo a
los sensores, para que volvieran a valores similares medidos en la etapa de
experimentación.

3. Cuando se empezó a desarrollar las mediciones en los diferentes usuarios, se
observó que los pacientes generaban un estrés en la mano y se fatigaban con
mayor facilidad cuando el tiempo para la medición de cada sensor era de 1
minuto, por lo que se desarrolló una medición más corta de 30 segundos para
cada sensor, lo cual generó un menor estrés en cada uno de los pacientes y con
ello una mejor facilidad y aceptación por parte de ellos al desarrollar los
diferentes ejercicios.

4.Para la toma de muestras de cada paciente se observó que el sensor
electromiográfico tenía una mejor respuesta de captura con los electrodos de
único uso. Lo anterior sucedió porque tenía un mejor pegante, frente a los
electrodos que se podían reusar, dado que los reutilizables no generaban un
buen contacto y así se perdía parte de la señal cuando los usuarios generaban
fuerza de agarre.

4. Se observó que la correlación entre las diferentes variables está en un nivel
moderado y tenue lo que permitió generar el análisis estocástico en la red
neuronal artificial, además se visualizó que algunas gráficas tenían una
distribución normal por medio de la función pairplot de python.

5. Se visualizó que es fundamental preguntar a los diferentes pacientes por
posibles alergias a algún material como el caso del velostat o a los electrodos de
contacto, ya que se visualizó un caso atípico donde la usuaria comentó que
podría tener alergias, lo que permitió un proceso más ágil en la prueba, para
disminuir posibles molestias al paciente.

6. En el análisis de la red neuronal se visualizó que el número de capas ocultas y
neuronas podrían hasta cierto punto optimizar el desempeño de la red, sin
embargo cuando son un número significativo, pasan por cierto umbral de
entrenamiento y ya no tienen un rendimiento correcto, por la carga
computacional y el tiempo de respuesta de las diferentes arquitecturas.

7. Se deja como trabajo futuro el desarrollo de algoritmos computacionales con
deep learning, además de algoritmos enfocados en otras variables de
experimentación con el propósito de abarcar momentos puntuales de la
evolución de personas con probabilidad de síndrome de túnel carpiano, como es
el caso de personas con tendinitis, debilidad y fatiga muscular.


























