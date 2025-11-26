# Maximización del Accuray en el modelo CNN
Para maximizar el accuracy en la validación se agregó, en primer lugar, Batch Normalization a las capas convolucionales. Esta técnica normaliza las activaciones intermedias dentro de cada batch, lo que reduce la variabilidad interna de las distribuciones y estabiliza el gradiente. Esto produce una convergencia más rápida y favorece al aumento en la accuracy tanto en entrenamiento como en validación.

También se incorporó la transformación ShiftScaleRotate() como parte del data augmentation. Esta técnica desplaza, escala y rota las imágenes de forma aleatoria, aumentando la variabilidad del conjunto de datos de entrenamiento. Al exponer al modelo a imágenes modificadas en posición, orientación y tamaño, se evita que aprenda patrones excesivamente específicos; reduciendo el riesgo de overfitting y mejorando la accuracy sobre datos no vistos. El data augmentation se complementó, además, con transformaciones como Horizontal Flip, Vertical Flip y Random Brightness/Contrast.

Por otro lado, se utilizó Early Stopping con una paciencia de cinco épocas para detener automáticamente el entrenamiento cuando el accuracy de validación dejara de mejorar. Aunque esta implementación no incrementa directamente el accuracy, evita el sobreentrenamiento y garantiza que el modelo conserve su mejor versión durante el proceso de optimización.

De esta manera, se obtuvieron 3 modelos con accuracy en validación mayor al 61%. Dentro de estos, el segundo modelo implementado mostró las mejores métricas, alcanzando un accuracy del 65,19% durante la validación y del 73,17% en el entrenamiento. Asimismo, la loss para este modelo en validación resultó igual a 0.97. Las curvas correspondientes se visualizan a continuación.

<img width="933" height="367" alt="Captura de pantalla 2025-11-25 a la(s) 11 50 13 p  m" src="https://github.com/user-attachments/assets/2b9643bd-11c7-47a5-a265-77a61229fe25" />

<img width="932" height="368" alt="Captura de pantalla 2025-11-25 a la(s) 11 50 36 p  m" src="https://github.com/user-attachments/assets/a6ab1ddf-015a-4b4f-af23-ef22bc87ab61" />
