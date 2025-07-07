# codigo_tfm_Roger

### Información del código de las carpetas:

1) genero: Se entrena un modelo de clasificación sobre el dataset de UTKFace para estimar el género (masculino o femenino) a partir de imágenes de caras.

2) raza: Se entrena un modelo de clasificación sobre el dataset de UTKFace para estimar la raza (las razas son blanco, negro, asiatico, hindú y otro)

3) emocion: Se entrena un modelo para intentar identificar la emoción de una persona de entre 8 emociones posibles (enfado, asco, miedo, alegría, tristeza, sorpresa, neutral, desprecio).

4) deepfake: Usando la arquitectura MesoNet y el dataset de deepFake de kaggle, se entrena un modelo de clasificación que predice muy bien si una imagen es real o si por el contrario se trata de un fake.

5) edad: Se entrena un modelo de regresión sobre el dataset de UTKFace para estimar la edad a partir del rostro.

6) deteccion_caras: se entrena yolov5 sobre WiderFace dataset para detectar las caras. Se entrena una arquitectura bastante grande y robusta (yolov5x.pt)

7) deteccion_personas: se extraen anotaciones de las bounging boxes para personas (del dataset de COCO) y se entrena yolov5 sobre ese dataset, logrando detectar de modo bastante efectivo a las personas. En esta ocasión se uso una arquitectura más pequeña (yolov5m.pt) pero efectiva de todos modos. 

8) segmentacion_semantica_personas: se extraen anotaciones de las máscaras de segmentación para la clase persona del dataset de COCO. Se entrena un modelo de red basado en U-Net, obteniendo buenos resultados visuales y de métricas accuracy, iou y dice coefficient.

9) reconocimiento_facial: Usando el dataset de VGGFace2, se entrenó una red siamesa basada en GoogleNet que intenta decidir si dos imágenes son de la misma persona o de personas distintas. El coste del entrenamiento de este modelo es muy grande. 

10) vae_rostros: Se entrenó un autoencoder variacional para la generación facial sobre el dataset de CelebA. Se usó la implementación del VAE de: https://github.com/davidADSP/Generative_Deep_Learning_2nd_Edition/tree/main/notebooks/03_vae/03_vae_faces

11) progan_rostros: Se usó la implementación de ProGAN en PyTorch de https://github.com/TAUIL-Abd-Elilah/Generative-Adversarial-Networks--GANs/blob/main/progan-implementation-from-scratch-pytorch.ipynb . Se entrenó la arquitectura para la generación facial sobre el dataset de CelebA-HQ.

12) stylegan_rostros: Se usó la implementación de StyleGAN en PyTorch de https://github.com/TAUIL-Abd-Elilah/Generative-Adversarial-Networks--GANs/blob/main/StyleGAN%20implementation%20from%20scratch%20PyTorch.ipynb . Se entrenó la arquitectura para la generación facial sobre el dataset de CelebA-HQ.


### Información de los datasets:

1) dataset UTKFace: Se trata de un dataset en el que las imágenes de caras de personas vienen etiquetadas con el género, la edad y la raza. 

2) dataset AffectNet: Clasifica imágenes de rostros en base a ocho emociones; 
Clase 0: enfado (anger)
Clase 1: desprecio (contempt)
Clase 2: asco (disgust)
Clase 3: miedo (fear)
Clase 4: alegría (happy)
Clase 5: neutral (neutral)
Clase 6: tristeza (sad)
Clase 7: sorpresa (surprise)

Usamos una versión reducida del dataset, descargada de kaggle.

3) dataset Widerface. Se trata de un dataset con las anotaciones de las bounding boxes de las caras de las personas. Es un dataset ideal para entrenar modelos de detección de rostros. Se descargo de http://shuoyang1213.me/WIDERFACE/


4) dataset de Coco. Se trata de un dataset con anotaciones para detección y segmentación de 80 clases diferentes. En el trabajo se usó para entrenar yolov5 para detectar personas, y para entrenar una red parecida a U-NET para la segmentación semántica de personas en imágenes. El dataset puede descargarse de https://cocodataset.org/#download

5) deepfake dataset. Se trata de un dataset con imágenes de personas reales o fake (imágenes generadas por IA o imágenes que han sido alteradas (warped)). Puede descargarse de kaggle: https://www.kaggle.com/datasets/manjilkarki/deepfake-and-real-images  

6) dataset de VGGFace 2. Se trata de un dataset que muestra cientos de imágenes de unas 9000 personas diferentes. Se trata de un dataset ideal para estudiar los problemas de la verificación facial y el reconocimiento facial. El dataset original sólo pudo ser descargado a traves de torrent.

7) dataset de CelebA. Se trata de un dataset con imágenes de las caras de personas famosas. Se está usando en la parte de IA generativa para generar rostros mediante los autoencoders variacionales y mediante las GAN. Se puede descargar este dataset de Kaggle: https://www.kaggle.com/datasets/jessicali9530/celeba-dataset

8) dataset de CelebA-HQ. Se trata de un dataset de imágenes de alta calidad de celebridades (se trata de una mejora del dataset de CelebA). Se está usando en la parte de IA generativa para generar rostros mediante los modelos ProGAN y StyleGAN. Se puede descargar de https://www.kaggle.com/datasets/lamsimon/celebahq
