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

# Proyecto no guiado
Las aplicaciones móviles están en todas partes. Son fáciles de crear y pueden ser lucrativas. Debido a estos dos factores, se están desarrollando cada vez más aplicaciones. En este cuaderno, realizaremos un análisis exhaustivo del mercado de aplicaciones de Android al comparar más de diez mil aplicaciones en Google Play en diferentes categorías. Buscaremos insights en los datos para idear estrategias que impulsen el crecimiento y la retención.

Vamos a echar un vistazo a los datos, que constan de dos archivos:

apps.csv: contiene todos los detalles de las aplicaciones en Google Play. Hay 13 características que describen una aplicación dada.

user_reviews.csv: contiene 100 reseñas para cada aplicación, las más útiles primero. El texto en cada reseña ha sido preprocesado y se le han atribuido tres nuevas características: Sentimiento (Positivo, Negativo o Neutral), Polaridad del Sentimiento y Subjetividad del Sentimiento.

# Instrucciones
- 1 Import the data, drop duplicate rows, and inspect the data.

	- Load datasets/apps.csv into a DataFrame and assign it to the variable  apps_with_duplicates.
	- Drop all duplicate rows from apps_with_duplicates and assign the result to apps.
	- Print the total number of apps.
	- Finally, display a random sample of 5 rows from apps.

- 2 Clean the dataset.
	- Create a list named chars_to_remove that contains the following characters: + , and $.
	- Create a list named cols_to_clean that contains the following column names: Installs and Price.
	- For each column in cols_to_clean in the apps DataFrame, replace each character in chars_to_remove with the empty string ''.
	- Finally, print a summary of the apps dataframe using the info() function. Observe the output.
- Task 3 
	- Convert Installs and Price columns to float data type using astype() function.
	- Verify the corrected data types by using the dtypes attribute of apps dataframe. (You can also reuse the info() function to verify the corrected data types)
- 4 Create data for a bar chart that shows the distribution of apps across different categories.

	- Find the number of unique app categories. Save your result in num_categories.
	- Count the number of apps in each category and then sort the categories in descending order of app count. Save your answer in sorted_num_apps_in_category.
- 5 Create a plot annotation for average app rating.
Find the average app rating and assign it to avg_app_rating.
- 6 Examine the relationship between size, price, and rating of apps using jointplot().
Recall from Task #1 that we had observed some missing values in the Rating and Size columns. To make rational decisions, it is important that we do not consider these missing values in our analysis. We will work with a subset apps_with_size_and_rating_present DataFrame for this task.

	- Select rows from apps where both Rating and Size values are present, ie - they are not null. Store the result in the apps_with_size_and_rating_present dataframe.
	- From apps_with_size_and_rating_present, select the categories having atleast 250 apps. Assign the result to large_categories dataframe.
	- Fill out x and y to create a joint plot of Rating as a function of Size.
	- From apps_with_size_and_rating_present dataframe, select all Paid apps. Save the result in paid_apps.
	- Fill out x and y to create a joint plot of Rating as a function of Price.
- 7 Use a strip plot to visualize the distribution of paid apps across different categories.

	- Plot a strip plot with x-axis extending along the Price range and y-axis depicting the Category.
	- Find apps priced above $200. Print the Category, App and Price columns for such apps.
- 8 Filter out "junk" apps.
Note: For simplicity, we will continue to use the popular_app_cats dataframe (from previous task) and not our original dataframe apps

	- Select rows from popular_app_cats that contain apps priced below $100 and assign it to apps_under_100.
	- Re-plot your strip plot using apps_under_100 dataframe (instead of popular_app_cats used in the previous task).
- 9 Prep the data for a box plot that compares the number of installs of paid apps vs. number of installs of free apps.

	- From apps, filter rows where for Type == Paid, and select the Installs column and assign it to y of trace0.
	- From apps, filter rows where for Type == Free, and select the Installs column and assign it to y of trace1.
- 10 Load the user review data and plot it to visualize sentiment of paid vs. free apps.

	- Read datasets/user_reviews.csv into the reviews_df DataFrame.
Merge apps and reviews_df DataFrames and assign the result to merged_df.
	- Create a box plot with Type on the x-axis and Sentiment_Polarity on the y-axis.



## Acerca de

Este proyecto fue creado por Misael González Soria y forma parte de mi curso de ingeniería en caracteristicas.