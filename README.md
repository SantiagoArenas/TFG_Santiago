# TFG Santiago Arenas

De momento estoy basando el proyecto en [este paper](support/Current_Paper.pdf).

## Fuentes de datos
[Summer Products and Sales Performance in E-commerce on Wish](https://data.world/jfreex/summer-products-and-sales-performance-in-e-commerce-on-wish), tiene algo de advertising pero es en otra plataforma, Wish.
En el repositorio está [dataAcquisition/AmazonSaleReport.xlsx](dataAcquisition/AmazonSaleReport.xlsx), que es el trabajo del máster de Facebook, se puede hacer algo parecido. 
Lo máximo que he encontrado ha sido análisis de reviews, [Amazon Product Review Dataset](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews), no me parece algo que pueda sacarse provecho.

Hay más cosas de ratings, pero tampoco lo veo muy útil: [Amazon Product Reviews](https://www.kaggle.com/datasets/skillsmuggler/amazon-ratings)
Más cosas que puede ser que sirvan, pero no son de amazon: [Online Retail Dataset](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store)
   
No solo de amazon, pero [E-commerce Sales and Ad Spend](https://data.world/)

UCI Machine Learning Repository, [Online Shoppers Purchasing Intention Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset)

El dataset de [facebookExploration](dataAcquisition/Facebook/facebookExploration.ipynb) No es una time series al no tener datos de tiempo.

## Códigos
Al principio me estoy centrando en explorar los distintos datasets para decidir cuál hacer. Esto está hecho en [dataAcquisition](dataAquisition)
### En el paper de referencia.
- *Time Series Models Sales Forecasting*: "forecasting sales is most suited for this format as they are widely used in and efficient in identifying seasonal patterns", 2.3.
- *ARIMA, Auto regressive moving average*: técnica de time series que analiza la dependencia entre la observación y los valores previos, diferencia las observaciones para hacer la tabla de tiempos estacionaria y usa la dependencia y error residual aplicado a observaciones pasadas. Funciona bien para valores que son muy cíclicos, pero falla cuando hay seasonality, aunque en el paper digan lo contrario. Para aprender a utilizar esto, estoy "siguiendo" el github [2-Arima](https://github.com/microsoft/ML-For-Beginners/blob/main/7-TimeSeries/2-ARIMA/README.md).
- *SARIMA, Seasonal-ARIMA*: lo mismo pero identifica seasonality.
- *LTSM, Long-Short Term Memory*: Identifican dependencias en el largo plazo, y se tienen en cuenta para que no afecten al modelo. Es mejor que una regresión logística tradicional y SVM, viene ya en un paper así que no tendríamos por qué demostrarlo nosotros, 2.6. 
- *Facebook Prophet*: open source, hace una regresión especial que tiene en cuenta datos que faltan, outliers, patrones temporales de vacaciones y temporales de seasonality.
