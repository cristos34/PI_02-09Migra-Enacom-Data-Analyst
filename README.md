<p align=center><img src=https://assets.soyhenry.com/logos/LOGO-HENRY-04.png><p>

# <h1 align=center> **PROYECTO INDIVIDUAL Nº2** </h1>

# <h1 align=center>**`Data Analyst`**</h1>

*Cristian Andres Contreras*  
*Negociante Internacional*  
*Data Sciencie(In progress)*

<p align="center">
<img src="https://miro.medium.com/v2/resize:fit:730/1*Hu4TWEt6o3iAWeqxqklbZg.jpeg"height=500>

</p>



<hr>  
Este trabajo consiste en realizar un análisis completo del comportamiento del sector de telecomunicaciones de una empresa Argentina, el cual se usan los datos de la API del organismo público de Argentina llamado **ENACOM**, quién suministra toda la información concerniente a las telecomunicaciones como son: los datos históricos del mercado, oferta, demanda y cobertura de los servicios de conectividad y tecnologías.

<hr>

## **Descripción del problema**

<p align="center">
<img src="https://presscoaching.com/wp-content/uploads/2018/10/problemas.jpg"height=300>

La industria de las telecomunicaciones ha jugado un papel fundamental en el desarrollo de los mercados a nivel mundial, lo que no sería diferente para Argentina que ha permitido el crecimiento del país, el ingreso y creación de nuevas empresas, que en su mayoría dependen de estos servicios.

En comparación con la media mundial, Argentina está en vías de alcanzar a la media mundial en el desarrollo de las telecomunicaciones, teniendo para el 2020 un total de 62,58 Mbps de velocidad promedio de descarga  general, debido a esto y a otros esenarios como por ejemplo, la comparación entre Brasil y Argentina; donde Argentina para el 2020 tiene en conexión de banda ancha con FTTH para hogares un porcentaje de instalaciones de 14%; mientras que, Brasil posee el 46.5%. Teniendo en cuenta, esta información, es necesario hacer un análisis global del comportamiento de esta industria, con el fin de encontrar nuevas tendencias y tomar decisiones acorde a la demanda. [Informacion_Externa](https://www.iprofesional.com/tecnologia/369031-por-que-argentina-se-quedo-atras-en-expansion-de-la-fibra-optica)

​<hr> 

## **Pasos para la elaboración del proyecto**
**1. Conexión a la API de Enacom**

Para conectarse a dicha API es fundamental tener claro cómo armar el request y sus requerimientos, los cuales son:  

#### **Acceder a la API :**
* **Paso 1.**  
 Este es enlace [link_Api](https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/) para acceder a la API 

* **Paso 2.**  
 Escoger la información que se necesita

* **Paso 3.**  
 Conocer cómo se arma la ruta para conectarse a los datos [link_Documentacion](https://junar.github.io/docs/es/_sections/03-conjunto_de_datos.html)

* **Paso 4.**  
 Clave que necesitarás para cada request, se encuentra en la API de ENACOM [link_clave](https://datosabiertos.enacom.gob.ar/developers/).

* **Número Guid :** (**NUMER-GEOGR**) el [GUID](https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/) del dataset que estás accediendo, este GUID lo puedes encontrar en la página del detalle de la vista, haciendo una búsqueda de la vista a través de la API y en muchos otros lugares.

* **Ejemplo**  
    http://api.datosabiertos.enacom.gob.ar/api/v2/dashboards/ colocar el [GUID](https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/) .csv/?auth_key= colocar [clave](https://datosabiertos.enacom.gob.ar/developers/)
<hr>


## **2. Recolección de datos**

La API brinda 16 dataset que contienen información relacionada con la conectividad en las diferentes provincias de Argentina, como se muestaran a continuación:

* **Penetración de Internet fijo (accesos por cada 100 hogares) :**  Número de accesos al servicio de Internet fijo por cada 100 hogares por provincia.

* **Penetración por hogares nacional de Internet fijo :** Serie trimestral de la penetración del Internet fijo en la métrica por cada 100 hogares.

* **Total nacional de accesos a Internet fijo por banda ancha y banda angosta :** Número total de accesos al servicio de Internet fijo por banda ancha y banda angosta (trimestral).

* **Accesos a banda ancha y banda angosta por provincia :** Número de accesos al servicio de Internet fijo por banda ancha y banda angosta en cada provincia (trimestral).

* **Serie trimestral de accesos a Internet fijo por tecnología :** Número de accesos al servicio de Internet fijo por tipo de tecnología. Total nacional (trimestral).

* **Acceso a Internet fijo por tecnología y provincia :** Número de accesos al servicio de Internet fijo por tipo de tecnología en cada provincia (trimestral).

* **Velocidad Media de bajada de Internet fijo :** Serie histórica de la velocidad media de descarga de Internet nacional (trimestral).

* **Velocidad media de bajada de Internet fijo por provincia :** Serie histórica de la velocidad media de descarga de Internet por provincia (trimestral).

* **Distribución de los accesos totales nacionales a Internet fijo por velocidad :** Distribución de los accesos totales nacionales a Internet fijo por velocidad de bajada (último trimestre disponible).

* **Acceso a Internet Fijo por rangos de velocidad de bajada y provincia :** Número de accesos al servicio de Internet fijo por velocidad de bajada en cada provincia (trimestral).

* **Accesos a Internet fijo por velocidad bajada y provincia :** Número de accesos al servicio de Internet fijo por velocidad de bajada en cada provincia.

* **Ingresos trimestrales por la prestación del servicio de Internet fijo :** Ingresos trimestrales de los operadores por el servicio de Internet fijo.

* **Accesos a Internet fijo por velocidad de bajada y localidad :** Número de accesos al servicio de Internet fijo por velocidad de bajada en cada localidad declarada.

* **Accesos a Internet fijo por tecnología y localidad :** Número de accesos al servicio de Internet fijo por tecnología en cada localidad declarada Categoría.

* **Listado de localidades con conectividad a internet :**
 Listado de localidades con conectividad a internet, con detalle por tipo de conexión.

* **Conectividad al servicio de Internet :** Consulta las tecnologías disponibles en tu localidad para acceder al servicio de Internet fijo y móvil.

<hr>

## **3. EDA**

Para realizar el análisis exploratorio se utilizó la herramienta **Python** para ir al [Documento](https://github.com/cristos34/PI_02-09Migra-Enacom-Data-Analyst/blob/main/EDA_TELECOMUNICIONES.ipynb) y **Power BI**, la cual estaba conectada a la API, una vez descargados los dataset se procede a analizarlos con la finalidad de distinguir los datos que tenían y a partir de ello escoger cuáles serían más convenientes; posterior a esto, se determina que sólo se trabajaran con 6 dataset que manejan información general y de esta manera se evita redundancia en los datos, dichos dataset son:

* **Penetración de Internet fijo (accesos por cada 100 hogares).**

* **Accesos a banda ancha y banda angosta por provincia.** 

* **Ingresos trimestrales por la prestación del servicio de Internet fijo.**

* **Acceso a Internet fijo por tecnología y provincia.**

* **Velocidad media de bajada de Internet fijo por provincia.**

* **Distribución de los accesos totales nacionales a Internet fijo por velocidad.**

* **Adicionalmente se creó un dataset de fechas con el fin engranar los anteriores dataset**


Teniendo claro que, con los datos que se trabajaran, se procede a realizar la limpieza y correción de los mismos, eliminando valores vacíos, cambiando datos erróneos y en power bi creando las relaciones entre las diferentes tablas. 
<hr>

## **3. Creación de visualizaciones**

[Visualizaciones](https://github.com/cristos34/PI_02-09Migra-Enacom-Data-Analyst/blob/main/Dasboar.PNG)

Para crear las visualizaciones se utlizó la herramienta **Power BI**, en la cual se crearon las relaciones de cardinalidad entre las diferentes tablas, buscando crear interacciones entre las mismas y crear un Dashboard interactivo, como se evidencia en el siguiente [archivo](https://github.com/cristos34/PI_02-09Migra-Enacom-Data-Analyst/blob/main/PI_02_09.pbix), como también se relizó un [informe](https://github.com/cristos34/PI_02-09Migra-Enacom-Data-Analyst/blob/main/Informe%20general%20ENACOM%20(Contreras).pdf) dónde se analiza el  tablero_de_control más unas [diapositivas](https://github.com/cristos34/PI_02-09Migra-Enacom-Data-Analyst/blob/main/CAC%20PRESENTACION.pdf) de presentacion.
