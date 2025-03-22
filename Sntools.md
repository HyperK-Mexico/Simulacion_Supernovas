## Sntools: Generación de eventos 


`Sntools` es un generador de eventos Monte Carlo para interacciones de neutrinos de supernova. Usa flujos de neutrinos
dependientes del tiempo y la energía de distintos modelos para simular interacciones dentro de un detector 
y generar archivos de eventos, que luego pueden usarse en simulaciones más detalladas.  

Inicialmente desarrollado para Hyper-Kamiokande, `Sntools` se amplió para soportar diferentes detectores y materiales. 
Además de su uso como aplicación de línea de comandos, también puede emplearse como una biblioteca de Python para modelar 
interacciones de neutrinos.

Para mas informacion detallada, visite la pagina oficial en github del programa creado por Jost Migenda (https://github.com/SNEWS2/sntools)


## Instalación

Se requiere tener `>= python 3.8`, en la terminal, se inserta el siguiente comando
```sh
$ pip install sntools
```
Para asegurarnos que se intalo de manera correcta se ejecuta el siguiente codigo
```sh
$ python -c ’import sntools; sntools.setup()’
```

## Ejemplo

Para generar eventos de neutrinos en supernova, se descarga la carpeta `fluxes/intp2001.data`, este contiene el flujo de los neutrinos en su formato `nakazato`
en la terminal ejecutamos los siguiente:
```sh
 $ sntools fluxes/intp2001.data --format nakazato --endtime 50
```
Este genera eventos en los primeros 50 ms (milisegundos) de la supernova basado en su flujo de neutrinos con un progenitor de 20 $M_{\odot}$ y los escribe en un formato `.kin` los resultados.

> **Nota:** Para mas información del modelo Nakazato, acudir a su pagina oficial http://asphwww.ph.noda.tus.ac.jp/snn/ , ademas de su articulo
> Nakazato et al., Astrophys. J. Supp. 205 (2013) 2, arXiv:1210.6841 [astro-ph.HE]

Si queremos una simulacion mas realista y demostrar lo que tiene que ofrecer sntools, se ejecuta lo siguiente: 
```sh
$ sntools fluxes/intp2001.data --format nakazato --channel es --detector SuperK --distance 20 --verbose --output intp2001es.kin
```
## ¿Que más ofrece Sntools?
- Material del detector
- Configuración del detector
- Canales de interacción
- Modelo de oscilación de neutrinos
- Formatos de entrada

Los formatos principales que maneja sntools son los siguientes:
- Nakazato
- Warren2020
- Gamma
- Princeton
- Totani

Ademas, el usuario puede generar su propia configuracion de detector, los materiales y canales de interacción, esto modificando los archivos internos del programa.

