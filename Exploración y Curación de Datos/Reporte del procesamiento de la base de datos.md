## Criterios de exclusión de ejemplos 
1. Se eliminaron las filas donde las propiedades con más ambientes (Rooms) que habitaciones (Bedroom2)
2. Se eliminaron las filas donde las propiedades tenian 0 habitaciones y 10 o más habitaciones
3. Se eliminaron los ejemplos con 6 o más lugares para autos
4. Se consideran los ejemplos de propiedades que fueron construidas a partir de 1850 y hasta 2017
## Caracteríticas seleccionadas
### Características categóricas
- Suburb: suburbios. 9 valores posibles. 
- Property Type: se agrega el tipo de propiedad descripto por la plataforma AirBnB en el mismo código postal. 4 valores posibles. [Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=cleansed_listings_dec18.csv) 
*Todas las características fueron codificadas con el método OneHotEncoding considerando en caso de Suburb las 9 categorías más frecuentes y en caso de Property Type, todas sus categorías*
### Características numéricas
- Rooms: cantidad de espacios y habitaciones aparte del baño y la cocina.
- Price: precio en dólares de la propiedad
- Distance: cercanía al centro de la ciudad en km.
- Bedroom2: cantidad de habitaciones.
- Bathroom: cantidad de baños. 
- Car: cantidad de espacios para poner el auto. 
- Landsize: tamaño del terreno donde esta la propiedad en metros cuadrados.
- YearBuilt: año de construcción de la propiedad. 
- Lattitude: coordenadas de latitud de la ubicación de la propiedad. 
- Longitud: coordenadas de longitud de la ubicación de la propiedad
-  Postcode: código postal 
-  BuildingArea: cantidad de metros construidos dentro del terreno
-  Rent Price mean: se agrega el precio promedio de las publiaciones de la plataforma AirBnB en el mismo código postal. [Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=cleansed_listings_dec18.csv) 
-  Rent price min:  se agrega el precio mínimo de las publiaciones de la plataforma AirBnB en el mismo código postal. [Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=cleansed_listings_dec18.csv) 
-  Rent price count: se agrega cantidad de precios de las publiaciones de la plataforma AirBnB en el mismo código postal. [Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=cleansed_listings_dec18.csv) 
-  Review Scores Rating median: se agrega la mediana de la calificación de las publiaciones de la plataforma AirBnB en el mismo código postal. [Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=cleansed_listings_dec18.csv) 
### Transformaciones 
1. Todas las características numéricas fueron estandarizadas
2. Las columnas 'YearBuilt', 'BuildingArea' y 'Landsize' fueron imputadas utilizando la instancia IterativeImputer para imputar múltiples variables con un estimador KNeighborsRegressor. 
3. Los valores de las características numéricas de la matriz obtenida luego de imputar los datos faltantes fueron reescalados a su formato original
4. Se escalaron los datos de las caracteríticas numéricas de la matriz obtenida luego de imputar los datos.
5. Se aplicó el método PCA para obtener los $n$ componentes principales de la matriz. 
### Datos  
1. Se agregan las 3 primeras columnas obtenidas a través del método de PCA, aplicado sobre el conjutno de datos totalmente procesado. 

