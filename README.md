# Proyecto guiado
Data camp link: https://app.datacamp.com/learn/projects/1833

Walmart es la tienda minorista más grande de Estados Unidos. Al igual que otros, han estado expandiendo su parte de comercio electrónico en el negocio. A finales de 2022, el comercio electrónico representó un impresionante total de 80 mil millones de dólares en ventas, lo que equivale al 13% del total de las ventas de Walmart. Uno de los principales factores que afecta sus ventas son los días festivos, como el Super Bowl, el Día del Trabajo, el Día de Acción de Gracias y la Navidad.

En este proyecto, La tarea es crear un pipeline de datos para el análisis de la demanda y la oferta en torno a las festividades y realizar un análisis preliminar de los datos. Se trabajara con dos fuentes de datos: las ventas de comestibles y datos complementarios. Se proporciona la tabla de ventas de comestibles en la base de datos PostgreSQL y un archivo extra_data.parquet que contiene datos complementarios.

La base de datos PostgreSQL no es suministrada por DataCamp y solo está accesible en su sitio web.

# Instrucciones:
- The extract() function should combine grocery_sales table and extra_data.parquet file. It should return a DataFrame and be stored as the merged_df variable.
- Thetransform() should take the merged_df as input, fill missing values, add a column "Month", keep the rows where the sales are over $10,000, and drop the index. Ultimately, it should return a DataFrame and be stored as the clean_data variable.
- The avg_monthly_sales() should take clean_data as input and returns an aggregated DataFrame containing two columns - "Month" and "Avg_Sales" (rounded to 2 decimals). You should store it as the agg_sales variable.
- The load() function should take in the cleaned and aggregated DataFrames, and their paths and saves them as clean_data.csv and agg_data.csv respectively, without an index.
- Finally, the validation() function should check whether the two csv files from the load() exist in the current working directory.




## Acerca de

Este proyecto fue creado por Misael González Soria y forma parte de mi curso de ingeniería en caracteristicas.