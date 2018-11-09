La transferencia de estilo es la técnica de recomponer imágenes al estilo de otras imágenes. Estos se crearon en su mayoría utilizando el código de [Justin Johnson](https://github.com/jcjohnson/neural-style) basado en el documento de [Gatys, Ecker y Bethge](https://arxiv.org/abs/1508.06576) que demuestra un método para rediseñar imágenes utilizando redes neuronales convolucionales.

![alt text](https://raw.githubusercontent.com/jjups96/fast-style-transfer/master/examples/thumbs/la_muse.jpg "Logo Title Text 1")

"En arte, especialmente en pintura, los seres humanos han dominado la habilidad de crear experiencias visuales únicas a través de la composición de una interacción compleja entre el contenido y el estilo de una imagen. Hasta ahora, la base algorítmica de este proceso es desconocida y no existe ningún sistema artificial con capacidades similares. Sin embargo, en otras áreas clave de la percepción visual, como el reconocimiento de objetos y rostros, desempeño casi humano, se demostró recientemente mediante una clase de modelos de visión de inspiración biológica llamados Deep Neural Networks."

-Leon A. Gatys

¿Es esta magia o solo un aprendizaje profundo? Afortunadamente, esto no implica ninguna magia: la transferencia de estilo es una técnica divertida e interesante que muestra las capacidades y representaciones internas de las redes neuronales.

El principio de la transferencia de estilo neuronal es definir dos funciones de distancia, una que describe cuán diferente es el contenido de dos imágenes, **content**, y otra que describe la diferencia entre las dos imágenes en términos de su estilo, **style**. Luego, dadas tres imágenes, una imagen de estilo deseada, una imagen de contenido deseada y la imagen de entrada (inicializada con la imagen de contenido), intentamos transformar la imagen de entrada para minimizar la distancia de contenido con la imagen de contenido y su distancia de estilo con el imagen de estilo.

En resumen, tomaremos la imagen de entrada base, una imagen de contenido que queremos hacer coincidir y la imagen de estilo que queremos hacer coincidir. Transformaremos la imagen de entrada base al minimizar el contenido y las distancias de estilo (**pérdidas/losses**) con la propagación hacia atrás (**backpropagation**), creando una imagen que coincida con el contenido de la imagen de contenido y el estilo de la imagen de estilo.

## EStilizacion de una imagen
Aplicamos varios estilos de pinturas a la rectoria de la unison.
<div align='center'>
<img src = 'examples/content/rectoria2.jpg' height="200px">
</div>

<div align = 'center'>
<a href = 'examples/style/wave.jpg'><img src = 'examples/thumbs/wave.jpg' height = '200px'></a>
<img src = 'examples/misResultados/rectoria2_wave.jpg' height = '200px'>
<img src = 'examples/misResultados/rectoria2_udnie.jpg' height = '200px'>
<a href = 'examples/style/udnie.jpg'><img src = 'examples/thumbs/udnie.jpg' height = '200px'></a>
<br>
<a href = 'examples/style/rain_princess.jpg'><img src = 'examples/thumbs/rain_princess.jpg' height = '200px'></a>
<img src = 'examples/misResultados/rectoria2_rain.jpg' height = '200px'>
<img src = 'examples/misResultados/rectoria2_muse.jpg' height = '200px'>
<a href = 'examples/style/la_muse.jpg'><img src = 'examples/thumbs/la_muse.jpg' height = '200px'></a>

<br>
<a href = 'examples/style/the_shipwreck_of_the_minotaur.jpg'><img src = 'examples/thumbs/the_shipwreck_of_the_minotaur.jpg' height = '200px'></a>
<img src = 'examples/misResultados/rectoria2_wreck.jpg' height = '200px'>
<img src = 'examples/misResultados/rectoria2_scream.jpg' height = '200px'>
<a href = 'examples/style/the_scream.jpg'><img src = 'examples/thumbs/the_scream.jpg' height = '200px'></a>
</div>

# Definamos estilo y representaciones.

-Modelo

--vgg19

-Definamos distancia

--Content loss

--Style loss
