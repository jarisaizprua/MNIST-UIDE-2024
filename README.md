# MNIST-UIDE-2024

El proyecto muestra cómo cargar, preparar, y utilizar un clasificador de árbol de decisión con el dataset MNIST, añadiendo una característica respecto a la suma de intensidades de píxeles, y evaluando el modelo a través de la precisión y una matriz de confusión. A continuación se detalla cada parte del script:

Grupo 4 - Integrantes
* Persona 1
* Persona 2
* Persona 3
* Persona 4
* Persona 4

Importación de Bibliotecas

    pandas: Utilizada para manejar los datos en formato tabular como DataFrames.
    train_test_split de sklearn.model_selection: Para dividir los datos en conjuntos de entrenamiento y prueba.
    DecisionTreeClassifier de sklearn.tree: El modelo de clasificación que se utilizará.
    accuracy_score, confusion_matrix de sklearn.metrics: Para evaluar el rendimiento del modelo.
    seaborn y matplotlib.pyplot: Bibliotecas para la visualización de datos, usadas aquí para mostrar la matriz de confusión.

Carga de Datos

    Se cargan los datos de entrenamiento y prueba desde archivos CSV, mnist_train.csv y mnist_test.csv, respectivamente.

Aplicar característica de suma de intensidades de píxeles

    Se añade una nueva característica llamada pixel_sum a ambos, el conjunto de entrenamiento y de prueba. Esta característica representa la suma de las intensidades de todos los píxeles de cada imagen, lo que podría ayudar al clasificador a distinguir entre dígitos basándose en su "densidad" o la cantidad total de tinta.

Preparación de los Datos

    Los datos se dividen en características (X_train, X_test) y etiquetas (y_train, y_test). La columna label, que contiene las etiquetas de los dígitos, se excluye de las características y se utiliza como el vector objetivo para el entrenamiento y la evaluación.

Entrenamiento del Modelo

    Se inicializa un DecisionTreeClassifier con un estado aleatorio fijo para reproducibilidad (random_state=42).
    El modelo se entrena (fit) con los datos de entrenamiento.

Evaluación del Modelo

    Se utilizan los datos de prueba para hacer predicciones con el modelo entrenado.
    Se calcula la precisión del modelo comparando las predicciones (y_pred) con las etiquetas reales (y_test) y se imprime.
    Se calcula y muestra la matriz de confusión para evaluar en detalle el rendimiento del modelo. La matriz de confusión compara las etiquetas predichas con las reales, proporcionando una vista de las clasificaciones correctas e incorrectas por categoría.

Visualización de la Matriz de Confusión

    Se utiliza seaborn.heatmap para visualizar la matriz de confusión. Esta visualización ayuda a identificar qué dígitos se clasifican correctamente y cuáles son comúnmente confundidos por el modelo; por ejemplo para el número 4, existieron 864 predicciones correctas mientras que dicho número fue predicho incorrectamente (confundido) con otros números de la siguiente manera:
    Número 0 -> 7 veces
    Número 1 -> 2 veces
    Número 2 -> 9 veces
    Número 3 -> 2 veces
    Número 5 -> 11 veces
    Número 6 -> 23 veces
    Número 7 -> 5 veces
    Número 8 -> 19 veces
    Número 9 -> 40 veces (mayor número de confusiones por la similitud visual que existe entre 4 y 9)
