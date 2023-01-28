<p align="center">

<img src="https://user-images.githubusercontent.com/109487557/215000302-b55a13f7-ecf4-4959-a89a-250f988e7fee.png"  height=400>
</p>





# <h1 align=center>  📋 Informe analytic 📋 </h1>
<hr>  

## Índice  

+ [Introducción.](#introducción)  
+ [Objetivos.](#objetivos)  
+ [Metas.](#metas)  
+ [Público_objetivo.](#público_objetivo)  
+ [Proceso_preliminar.](#proceso_preliminar)  
+ [Dashboard.](#dashboard)  
     - [Contexto.](#contexto)  
     - [Nivel_estratégico.](#nivel_estratégico)  
     - [Logística.](#logística)  
     - [Pareto_dinámico_vendedores.](#pareto_dinámico_vendedores)  


 <hr>  


## Introducción

  Tal como habíamos planteado en la primera entrega, hemos propuesto objetivos generales y específicos que sirven de horizonte para este proyecto. Es importante tenerlos bien en claro en todo momento para concentrar los esfuerzos en lograr que los mismos se cumplan. 

<hr>  

## Objetivos  

En grandes rasgos los objetivos específicos son 3:  
1.  **Ventas y recomendaciones**: Este objetivo pone en mira la situación financiera de nuestros clientes, de tal forma que olist pueda detectar tendencias de ventas y generar recomendaciones si fuera posible. A su vez, al poner a disposición esta información a los clientes buscamos que ellos generen sus propias estrategias 
2. **Logística:** La idea es entender el flujo de envíos de productos, y con ello generar focalizar esfuerzos para mejorar infraestructura, si fuese necesario, u otros servicios. (tiempos de entrega sobrestimados, sucursal, numero o margen de error para ver si es posible bajar el tiempo al que se compromete la empresa de pago)
3. **Soporte a los clientes:** Si a nuestros clientes les va bien en sus ventas, significa (en cierta medida) que el servicio que olist presta fue efectivo y por ende esperamos que se reutilice. Por tanto el objetivo se centra en ubicar quienes son los clientes que más aportan y quienes no, para poder brindarles una atención personalizada que les otorgue la percepción de que olist siempre está con ellos.

<hr>  

## Metas   

Este proyecto tiene como objetivo extraer información a través de herramientas de
visualización de datos para que las partes interesadas del proyecto puedan analizar y tomar
decisiones informadas, mejorando la eficiencia y maximizando las ganancias de la empresa.  

<hr>  

## Público_objetivo    
Los cuadros de mando y análisis desarrollados para el proyecto también están dirigidos a los
miembros de la organización responsables de la toma de decisiones. Al tratarse de un
comercio electrónico, estos usuarios tienen una mayor experiencia con la tecnología y la
utilizan a diario para aumentar su productividad. Además, los stakeholders de este proyecto
tienen una visión analítica del negocio, buscando nuevas oportunidades para incrementar las
utilidades de la empresa.  

<hr>  

## Proceso_preliminar  

Una vez los datos procesados y subidos a la Base de datos que esta en AWS los inyectamos en
Power Bi para usar las tablas.
Se aplico cierta limpieza a cada tabla para normalizarlas:
En general se saco la hora de las fecha para que no tenga conflicto con la tabla “calendario”
que creamos.
Se realizaron los siguientes cambios antes del análisis:

#### Tablas  


`olist_pf products:` Se adiciono una columna con los rangos de peso que tiene cada
producto para futuros análisis.

#### Se crearon las siguientes tablas adicionales:  

`Estados brasil:` Esta tabla contiene los estados de Brasil con su nombre completo y
abreviado. Se utiliza para tener los nombres completos de cada estado de Brasil.  
`Región customer:` Esta tabla contiene los nombres de regiones y estados de Brasil. Se
utiliza para agrupar a los compradores por región.  
`Geolocalización:` se creo una tabla con coordenadas latitud y longitud y código postal,
para conectar con el resto de las tablas y usar mapas.  
`Selectpareto:`Se utiliza para cambiar entre 70%, 80%, 90% la pagina donde se utiliza
Pareto.  
`Calendario:`Se creo un calendario de 2016 a 2018 para sincronizar las tablas.  

#### Tablas auxiliares para colocar métricas:  
`MedidasParetoProd:` Tiene las métricas que se utilizaron para realizar el Pareto del
dashboard “clientes”.  
`Medidas:` Tiene la mayoría de las métricas generales que se usan.  
`Medidaslog:` tiene las métricas que se usaron para la sección de “Logistica”.  
` MedidasParetoSeller:` Tiene las métricas que se utilizaron para realizar el Pareto de
“Sellers”.  
`Status:` Se utiliza para activar o desactivar el swich que cambia de modo claro a oscuro.  
`Status letra:` Se utiliza para acomodar el formato de títulos y subtitulos con los
cambios de colores.  

<hr>  

## Dashboard      

### Contexto:  

  Durante el período de 2016 a 2018

- Para el año 2016:  
  valor_corregido_2016 = (valor_original / (1 + inflación_2016))  

- Para el año 2017:
  valor_corregido_2017 = (valor_original / (1 + inflación_2016) / (1 + inflación_2017)) 
-Para el año 2018:
  valor_corregido_2018 = (valor_original / (1 + inflación_2016) / (1 + inflación_2017) / (1 + inflación_2018)) 


Para la creación del Dashboard se utilizó el software PowerBI, donde se crearon 2 Dashboards diferentes, uno enfocado en Olist y otro en sus clientes(vendedores).  
Una breve aclaración sobre los “KPIS”, los mismos se encuentran en un diccionario con la explicación y uso para cada uno. Se sugiere leerlo para una mayor comprensión del dashboard.  
`Diccionario KPIS`  
https://github.com/LucianoAsencio/PF05_Olist/blob/d25970fd6d2a662b6523b1326bf680d657c06091/Analytics/Diccionario%20Objetivos%20y%20KPIS.md   



**El dashboard enfocado a Olist:**  

##### Nivel_estratégico:  
Resume las principales métricas y KPIs del negocio a lo largo del tiempo y por región. Aquí tenemos una visión más integral del hecho de la venta y la consolidación de los valores más importantes para la rentabilidad del negocio.

<p align="center">

<img src="https://media.discordapp.net/attachments/1064924470072049755/1068350863841710090/image.png?width=1046&height=559"  height=400>
</p>

En base a los kpis realizados se puede ver un crecimiento en los ingresos del 21% respecto al año anterior, ingresos por fletes del 27% y un aumento del ticket medio en ingresos y fletes y en las metas propuestas. Tambien se  puede ver un aumento en las ordenes de 20%. Se obvervo que la mayoría de los pagos se realizan con tarjeta de crédito.  
- Sugerencia:  
Considerar promociones y campañas enfocadas en aumentar el uso de tarjeta de crédito como forma de pago.  

##### Logística
En cuanto a la logística, es importante analizar el tiempo de entrega y los envíos retrasados para ver cómo afectan a las ventas y los fletes.

<p align="center">

<img src="https://cdn.discordapp.com/attachments/1064924470072049755/1068361354127343726/image.png"  height=400>
</p>

Aunque en general se observa que la mayoría de las entregas se realizan a tiempo (98%), cuando hay retrasos, estos suelen ser de alrededor de 11.5 días.  
Sugerencia:
Se sugiere considerar promociones y campañas enfocadas en aumentar el uso de tarjeta de
crédito como forma de pago.  


<p align="center">

<img src="https://cdn.discordapp.com/attachments/1064924470072049755/1068361354127343726/image.png"  height=400>
</p>


Vemos que la mayoría de los clientes y vendedores son de la zona sureste del país por eso los precios de fletes y tiempo de esperas son menores, esto puede ser un factor por el cual la  mayoría de las ordenes sean de esta zona. 
En su contraparte los precios de flete y envío al norte son demasiado altos lo que provoca pocas compras. Esto se puede deber a la poca cantidad de vendedores en la zona y a que las bases logísticas están principalmente en el sur y sureste, lo que puede provocar mayor tardanza o costos de envíos en el norte.  

Sugerencia:  
Se recomienda analizar la posibilidad de expandir la presencia de vendedores en la zona norte del país para reducir los costos de envío y aumentar las compras en esa región. Además, se sugiere considerar estrategias para mejorar la eficiencia en la entrega de paquetes livianos, ya que son los que se compran con mayor frecuencia. Se puede considerar la posibilidad de negociar mejores tarifas con proveedores de transporte y/o establecer alianzas estratégicas con empresas locales.   


#### Pareto_dinámico_vendedores   

Pareto dinámico permite identificar a los vendedores que contribuyen en mayor medida al
rendimiento de las ventas, así como también los vendedores que tienen un menor
rendimiento y los que están inactivos.

<p align="center">

<img src="https://user-images.githubusercontent.com/109487557/215000079-06202a52-996d-480e-bc13-2fe02c30b3ea.png"  height=400>
</p>

Sugerencia  
Invertir recursos en el segmento de vendedores que representan el 22% de los ingresos, darles incentivos y mejorar su desempeño. También se recomienda analizar y tomar acciones en los 712 vendedores inactivos para aumentar su rendimiento y contribuir al crecimiento de los ingresos.



