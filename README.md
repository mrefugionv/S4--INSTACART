# S4--INSTACART
A partir visualizaciones gráficas dar respuesta a las preguntas de negocio de una plataforma de entrega de comestibles.

Data Wrangling : Lectura y exploración de datos. Manejo de tipos de datos, valores auscentes y valores duplicados.  Análisis de los datos. Visualización de datos.

## Descripción

Instacart es una plataforma de entregas de comestibles donde la clientela puede registrar un pedido y hacer que se lo entreguen, similar a Uber Eats y Door Dash.
A continuación se enlistan las preguntas presentadas por el cliente:
1. Número de personas que hacen pedidos dependiendo de la hora del día.
2. Qué día de la semana la gente hace sus compras.
3. Tiempo que la gente espera hasta hacer su siguiente pedido, y comenta sobre los valores mínimos y máximos.
4.  ¿Existe alguna diferencia entre las distribuciones `'order_hour_of_day'` de los miércoles y los sábados? 
5. Distribución para el número de órdenes que hacen los clientes (es decir, cuántos clientes hicieron cierta cantidad de pedidos).
6. ¿Cuáles son los 20 principales productos que se piden con más frecuencia?
7. ¿Cuántos artículos suelen comprar las personas en un pedido? ¿Cómo es la distribución?
8. ¿Cuáles son los 20 principales artículos que vuelven a pedirse con mayor frecuencia (muestra sus nombres e IDs de los productos)?
9. Para cada producto, ¿cuál es la tasa de repetición del pedido (número de repeticiones de pedido/total de pedidos?
10. Para cada cliente, ¿qué proporción de los productos que pidió ya los había pedido? Calcula la tasa de repetición de pedido para cada usuario en lugar de para cada producto.
11. ¿Cuáles son los 20 principales artículos que la gente pone primero en sus carritos (muestra las IDs de los productos, sus nombres, y el número de veces en que fueron el primer artículo en añadirse al carrito)?

## Herramientas utilizadas 
![Python](https://img.shields.io/badge/:Python-024A86?style=for-the-badge&logo=python&logoColor=white&labelColor=101010)</br>
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

![Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)


## Conclusiones 

La capacidad de poder visualizar los los datos dados en de una determinada base de datos, nos permite principalmente comunicar de una manera mucho más clara las respuestas a ciertas preguntas y obtener un panorama general del comportamiento de los datos. Poe ello la importancia de escoger adecuadamente el tipo de gráfica que representa mejor los datos y la claridad con que se presneta (un título descriptivo, ejes con etiquetas y unidades, que sean adecuadas y consistentes las escalas en los ejes y las leyendas).

A partir de visualizaciones gráficas se dieron respuesta a  las preguntas presentadas por el cliente:
1. Se hacen más pedidos entre las 9 y 17 hrs, siendo la hora pico las 10 de la mañana; y la menor proporcion de compras se genera entre las 11 y 6 hrs, siendo más notorio entre las 3 y 4 hrs.
2. Las ordenes no varían en grandes proporciones durante la semana, sin embargo se nota un aumento de ordenes en fin de semana, especialmente el domingo es el día que prefieren para hacer las compras.
3. El tiempo que tardan los usuarios en generar un nuevo pedido va de 0 (el mismo día) a 30 días. La preferencia es hacer los víveres cada mes (30 días) seguido por el grupo de personas que prefieren hacer la compra cada semana (7 días).
4. En general, las distribuciones para 'order_hour_of_day' de los miércoles y los sábados son similiares. Sigue un comportamiento parecido, con la más clara diferencia entre las 9 am y las 4pm, que es cuando los sábados aumenta en mayor proporción la cantidad de ordenes realizadas por los usuarios; Siendo el sábado a las 10 am cuando se disparan las ventas.
5. Observamos que es comun que los usuarios generen hasta 4 pedidos, a partir de ahí la gráfica disminuye exponencialmente, cada vez menos usuarios compran un pedido más, hasta llegar a 100 pedidos.
6. Los 20 productos más vendidos son : BANANA, BAG OF ORGANIC BANANAS, ORGANIC STRAWBERRIES, ORGANIC BABY SPINACH, ORGANIC HASS AVOCADO, ORGANIC AVOCADO, LARGE LEMON, STRAWBERRIES, LIMES, ORGANIC WHOLE MILK, ORGANIC RASPBERRIES, ORGANIC YELLOW ONION, ORGANIC GARLIC, ORGANIC ZUCCHINI,ORGANIC BLUEBERRIES, CUCUMBER KIRBY, ORGANIC FUJI APPLE, ORGANIC LEMON, APPLE HONEYCRISP ORGANIC, ORGANIC GRAPE TOMATOES. En ese orden, las bananas siendo las más pedidas.
7. Las personas suelen comprar entre 1 y 10 artículos por pedido, siendo  lo más común 5 productos. Va disminuyendo exponencialmente las personas que hacen pedidos  mayores a  10 artículos. El tope de artículos que hacen normalmente las personas es de 64.
8. Los 5 productos más vueltos a pedir son los mismos 5 productos más pedidos que hayamos en el apartado anterior, después nos encontramos con otros productos o bien en otro orden. Por lo el hecho de que un producto sea de los más vendidos no quiere decir que sea vuelto a comprar por el mismo usuario.
9. La mayor proporción (10%) de los productos tiene una relación de ser reordenado por las veces de ser pedido de un 0.5 por cierto, esto quiere decir que por cada dos veces que se compra fue vuelto a ordenar 1 vez.
10. La mayoría de los clientes tiende a pedir los mismos productos (proporción 1.0) recurrentemente.
11. Las personas suelen poner en su carrito, justamente los productos más populares : las bananas y bag of organic bananas.

## Profundización técnica
* Exploración de datos:  pd.read_csv ('', sep=';') , df.head(), .info(show_counts= True),
* * Verificar que los valores sean razonables- .describe(): max() , min()
* Preprocesamiento de datos:
* * Varifica y correge tipos de datos 
  *  Identifica y completa valores duplicados, ¿por columna o toda la fila? -
  *  * implicitos - df[col].str.upper() , 
     * explícitos -  .duplicated() , .drop_duplicates(inplcae=True).reset_index(drop=True)
  *  Identifica y completa valores auscentes, evitando la perdida de información. ¿Cómo se rlacionan entre ellos?¿qué pudo haber pasado?:
     *  .isna() , df[col].fillna(value,inplace=True) ,  df.dropna(subset=[col]) - eliminación de datos por auscencia en una columna en particular.
* Análisis de datos:
* * Graficas de dos ejes - g = df.groupby(by='col1')['col2'].count(),  g.plot (x='col1' ,y='col2'o ['col2','col3','col4'...], tittle='col2', kind='bar/scatter/', xlabel ='' ,rot=90, ylablel='', figsize=(#,#),color=''), plt.show()
  * * Visualizaciones claras 
  * Manejo de series - s = df[col].groupby(by='col1')['col2'].count/max/min..(), df = pd.concat(s1,s2,axis='columns'), df.colums =['s1','s2'], s.sortvalues(ascending=True/False)
  * Manejo de dataframes - df = pd.DataFrame(s/df), df_t = df1.merge(df2, on='col', how='inner/outer/left/right'), df[col].map(funcion) - recorrer celdas de col, df[new_col]=s 
