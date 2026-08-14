# Proyecto 1 Analisis de ConnectaTel
**Descripción:** Se analizó el comportamiento del negocio dentro de un rango especifico de tiempo, con el fin de construir un perfil estadístico del cliente así como los comportamientos atípicos de los mismos. Finalmente se construyó un segmento de clientes.

**Título:** Identificación y Análisis de Outliers mediante la segmentación de clientes.

- **Desafío:** El cliente necesitaba evaluar el comportamiento de los clientes para así diseñar estrategias de retención. 

- **Proceso:** Se inició con un análisis exploratorio, para identificar los tipos de datos, valores faltantes y familiarizarse con los datasets. El primer dataset solo contenía 40k registros, donde cada fila representaba el uso que cada cliente daba a su plan telefonico. El segundo dataset contenía 4k registros, donde cada fila representaba un usuario y su información. Finalmente el ultimo dataset solo contenía información sobre los planes ofrecidos.

  Ya con los datasets identificados, procedimos a verificar la calidad de datos, donde encontramos que había varias columnas con valores faltantes así como también sentinels. Se estandarizaron los tipos de dato y las columnas de texto. Se utilizaron columnas adyacentes para rellenar los datos nulos. Finalmente, en las columnas numéricas, se imputaron los datos faltantes haciendo uso de la mediana. Ya que es la que menos afectaba al análisis.

  Ya con los datos limpios y verídicos, procedimos a hacer agrupaciones para empezar a entender el comportamiento del usuario. Se realizó un Left JOIN que nos permitió unir el dataset de uso con el de clientes mediante la clave primaria de ID de usuario. Con el merge hecho comprendimos el porcentaje de uso por el tipo de plan del cliente. 

  Para facilitar el entendimiento del uso de planes por cliente se hicieron visualizaciones que no solo permitieron entender el comportamiento sino que también nos ayudo a localizar outliers. Hicimos uso de un IQR para identificar los rangos intercuartílicos y así entender la dispersión de los datos en la cantidad de llamadas, minutos de llamadas, etc. Con estas operaciones hechas pudimos verificar si mantendríamos o no los outliers. 

  Finalmente se segmento a los clientes por edad y por que tanto usaban su plan. Lo que nos permitió entender mas el comportamiento del cliente. 

- **Metodología:** Había valores nulos e inválidos en ciertas columnas. Age, date, city. Se convirtieron en NaN o NaT dependiendo el caso. Sin embargo se pudo comprobar que ciertos nulos dependían directamente de otras columnas, se imputaron y se mantuvieron. Columnas como reg_date y date estaban como float64, se tuvo que convertir a fecha para poder analizar los datos por año. Se estandarizaron fechas y formatos para asegurar un Join seguro. 

  
Columnas como reg_date y date estaban como float64, se tuvo que convertir a fecha para poder analizar los datos por año.
- **Insights:** De acuerdo a los datos obtenidos, la mayoría de los usuarios hacen un uso medio de los servicios que tienen. A pesar de que hay pocos usuarios que hacen un alto uso, este grupo modifica el análisis pues su uso esta por encima de los limites, bien puede ser algo de una sola vez, pero si se repitiera el patron, seria recomendable identificarlos.

Esto sugiere que el segmento que mas aporta es el grupo de adultos los cuales tienden a hacer un uso moderado de los servicios. Por otro lado a pesar de que un numero considerable de "adultos mayores" existe su uso de los servicios es bajo.

Se recomienda identificar al grupo pequeño de usuarios que hace un uso alto del servicio para darles tratamiento VIP.
Adicionalmente se recomienda hablar con el equipo de marketing, para incentivar al segmento de jóvenes, ya que mantienen un balance de uso y usuarios.
  
- **Resultado:** Al final se logro observar mediante el uso de matplotlib que la distribución de usuarios y uso era simétrica, pero se detecto que un segmento en especifico de clientes tendía a mejorar su plan de telefonía. Esto ayudó a tomar una decisión informada del negocio así como también proporcioné sugerencias basadas en el contexto del negocio que podrían ser tomadas en cuenta.
