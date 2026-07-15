# Clasificación de metástasis de cáncer de mama en ganglios linfaticos con Deep Learning en imágenes histológicas
![Uploading image.png…](1200w.avif)

Este Trabajo Fin de Master se ha desarrollado como fase final del máster de Ingeligencia Artificial cursado en la UNIR (España).



# Resumen

# Estructura del repositorio de código
- Este proyecto se ha creado con Poetry para la gestión de versiones de las diversas librerías usadas y sus dependencias (ficheros: poetry.toml, pyproject.toml y poetry.lock). Poetry.lock contiene las versiones exactas de todas las dependencias instaladas y pyproject.toml contiene las versiones de las librerias que nosotros manualmente instalamos con Poetry (instrucciones que ofrecemos a Poetry; pero para conocer versiones exactas instaladas consultar Poetry.lock)

Los ficheros que se encontrarán en el repositorio son los siguientes:

- 00_EDA_and_CNN.ipynb: Se realiza toda la fase de exploración de datos Como parte de este prirmer pipeline en el que probamos a entrenar diferentes configuraciones de redes neuronales convolucionales, evaluando los resultados obtenidos
- 01_uni_finetuning.ipynb: Se realizan dos pruebas con el modelo UNI.
+   UNI_1: Un primer pipeline en el que se usa el modelo UNI para la extracción de embeddings a partir de las imágenes y se entrena una red clasificadora que a partir de esos emneddings aprenda a predecir presencia o ausencia de cáncer
+   UNI_2: Se realiza un finetunning de las últimas dos capas del modelo UNI (encoder) y se entrena la red clasificadora como se hacía en el pipeline anterior
Ambos pipelines son evaluados en este notebook

Ficheros de datos del dataset PatchCamelyon utilizados (fuente: https://patchcamelyon.grand-challenge.org/Introduction/) :
- camelyonpatch_level_2_split_train_x.h5
- camelyonpatch_level_2_split_train_y.h5
- camelyonpatch_level_2_split_valid_x.h5
- camelyonpatch_level_2_split_valid_y.h5
- camelyonpatch_level_2_split_test_x.h5
- camelyonpatch_level_2_split_test_y.h5
Para este proyecto los archivos con metadatos del dataset no se han  utilizado pero se dejan en el repositorio por posible futura utilidad

- En la carpeta data se encuentran los datasets intermedios guardados despues de aplicar las transformaciones y Data Augmentation
- En la carpeta imagenes_guardadas_EDA_y_eval se encuentran guardadas plots e imágenes generadas en los notebooks.
- Por último hemos guardado los artefactos de los diferentes modelos entrenados:
+ CNN_1: mejor_cnn1_gpu.h5
+ CNN_2: mejor_cnn2.h5 y mejor_CNN2_segun_val_loss.h5 (El mejor modelo a guardar obtenido durante el entrenamiento se decide segun la metrica AUC, por eso también guardé el modelo resultante entrenado con la mejor val_loss por compararlos)
+ CNN_3: mejor_cnn3.h5
+ CNN_4: mejor_cnn4.h5
+ UNI_2: uni_finetuned_best.pt
+ UNI_1: uni_head_only_best.pt 

   
