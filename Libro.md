# Libro - Bioinformática genómica
___

**Nombre: Daniel Tichy**  
&nbsp;

# Índice
1. [Laboratorio 0: Instalación e Introducción a R](#1)
2. [Laboratorio 1: Análisis de secuencias mediante Bioconductor](#2)
3. [Laboratorio 2: Diseño de partidores](#3)
4. [Laboratorio 3: Ensamble de Genomas](#4)
5. [Laboratorio 4: Análisis de Expresión Génica](#5)
6. [Laboratorio 5: Metagenómica](#6)
7. [Laboratorio 6: Genómica de Poblaciones](#7)



## 1 
## Laboratorio 0: Instalación e Introducción a R 
Este Libro está pensando como tutorial para aquellas personas que deseen aprender a hacer uso básico de herramientas bioinformáticas para el análisis de datos biólogicos, ocupando como plataforma un ordenador con sistema operativo Linux, siendo esto último requisito obligatorio para el uso de las herramientas descritas a continuación. 

R es un lenguaje de programación enfocado al análisis estadístico.

Es de uno de los lenguajes más utilizados en investigación por la comunidad estadística, siendo además muy popular en el campo de la minería de datos, la investigación biomédica, la bioinformática y las matemáticas financieras. Esto se debe a la posibilidad de cargar diferentes paquetes con funciones de cálculo o graficos. R es parte del sistema GNU y se distribuye bajo la licencia GNU GPL. Está disponible para los sistemas operativos Windows, Macintosh, Unix y GNU/Linux.

Para instalar la última versión disponible de R primero debe modificar el archivo sources.list que se encuentra en la carpeta /etc/apt en su ordenador con sistema operativo Linuxy, con un editor de texto como gedit y agregar lo siguiente: 


    deb https://https://dirichlet.mat.puc.cl//bin/linux/ubuntu trusty/
    deb https://http://dirichlet.mat.puc.cl//bin/linux/ubuntu trusty/


Guarde los cambios, vuelva a su terminal e ingrese los siguientes comandos en su consola

    sudo apt-get update
    sudo apt-get install r-base 
  
Responda si, "Y" o "Yes" para descargar e instalar el paquete que contiene R, su terminal debería mostrar sin errores el progreso de la instalación, para verficiar que la instalación fue correcta ingrese lo siguiente a su consola: 

    R

y debería obtener lo siguiente en pantalla: 

    R version 3.3.1 (2016-06-21) -- "Bug in Your Hair"
    Copyright (C) 2016 The R Foundation for Statistical Computing
    Platform: x86_64-pc-linux-gnu (64-bit)

    R es un software libre y viene sin GARANTIA ALGUNA.
    Usted puede redistribuirlo bajo ciertas circunstancias.
    Escriba 'license()' o 'licence()' para detalles de distribucion.

    R es un proyecto colaborativo con muchos contribuyentes.
    Escriba 'contributors()' para obtener más información y
    'citation()' para saber cómo citar R o paquetes de R en publicaciones.

    Escriba 'demo()' para demostraciones, 'help()' para el sistema on-line de ayuda,
    o 'help.start()' para abrir el sistema de ayuda HTML con su navegador.
    Escriba 'q()' para salir de R

Posteriormente pasamos a instalar un asistente de R que nos ayudará a programar llamado Rstudio 
desde el siguiente link:https://www.rstudio.com/products/rstudio/download/

Y descargamos la última versión correspondiente a nuestro sistema operativo, al momento de confeccionar este tutorial 
dicha versión correspondía a RStudio 0.99.903 - Ubuntu 12.04+/Debian 8+ (64-bit), al ser un archivo .deb bastaría 
instalarlo mediante doble click al archivo en la carpeta de descarga. 

Una vez finalizada la instalación volvemos al terminal e ingresamos el siguiente comando 

    rstudio

El programa debería iniciarse y usted debería tener la siguiente imagen de la interfaz gráfica del programa. 

![Image of Figura 1](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/Rstudio imagen.jpg)

Para Introducirlo a R daremos a continuación algunos ejemplos que le permitirán comprender como funciona, ingrese lo siguiente en la consola de Rstudio (>) 

    3+5

Si ingresó el comando descrito lo siguiente debería aprecer en su consola 

    [1] 8

Lo que significa que usted acaba de crear un objeto que contiene un elemento unidimensional de magnitud 8, correspondiente a la suma de 3 más 5, no obstante como no asociamos este objeto a ninguna variable este objeto no se guardó y no podemos volver a trabajar con él, por lo que procederemos a asignarlo a una variable lo cual se hace con el operador " <- "o " -> " Ingrese lo siguiente a su consola:

    3+5->c

 Si realizó la operación correctamente debería aparecer en la pestaña derecha de la interfaz llamada Global Environment una tabla llamada Values donde en la primera columna tenemos el nombre del objeto recién creado "c" y su valor 8. 
 
 Para el siguiente ejercicio ingrese lo siguiente a su consola: 

    # Usted puede agregar comentarios a sus futuros scripts de R anteponiendo un gato (#) antes de comenzar a escribir 
    # Ahora asignaremos el valor 3 a la variable a 
    a <- 3
    # y el valor 5 a la variable b 
    b <- 5
    # Ahora a es 
    a
    # Ahora b es 
    b
    # y si sumamos a y b 
    a + b
    
Si realizó la operación correctamente usted debería visualizar lo siguiente: 

    # Usted puede agregar comentarios a sus futuros scripts de R anteponiendo un gato (#) antes de comenzar a escribir 
    # Ahora asignaremos el valor 3 a la variable a 
    a <- 3
    # y el valor 5 a la variable b 
    b <- 5
    # Ahora a es 
    3
    # Ahora b es 
    5
    # y si sumamos a y b 
    8 

Una vez entendido como funciona la declaración de variables y la creación de objetos en R pasaremos a ver la funciones. 
Como en todo lenguaje de programación, en R las funciones se componen de dos partes, la función misma( F() ) y su argumento (A)
ejemplo: F(A), una función F cuyo argumento es A. Como primer ejecicio digite lo siguiente en su consola: 

    round(3.14159)
    
 Lo que debería entregarle como resultado lo siguiente: 

    [1] 3

Lo que acaba de hacer es usar la función, round, que como su nombre indica redondea el número decimal que se le de como primer argumento, no obstante al igual que otras funciones, round puede tomar más de un argumento por ejemplo, ingrese lo siguiente en su consola:

    round(3.14159, digits=2)
    
Lo que debería entregarle como resultado lo siguiente 

    [1] 3.14

Como debe intuir, en el segundo argumento indicamos a la función round cuantos decimales permitir antes de redondear. 

Una vez entendido como indetificar y utilizar una función en R pero antes de empezar a procesar data con estas repasaremos cuales son los tipos de datos y las estructuras de estos que existen en R. 

####Vectores 
Los vectores son la estructura de dato más común en R y su caballo de trabajo principal, de hecho los primeros ejercicios que realizamos se hicieron con vectores. Los vectores como vimos pueden contener distintos tipos de datos, como por ejemplo números, como ejercicio ingrese lo siguiente en su terminal: 

    glengths <- c(4.6, 3000, 50000)
    glengths

Al ingresar el nombre del vector como recordará, se mostrará su contenido, en este caso

    [1] 4.6  30000.0  500000.0 


Los vectores también pueden contener palabras 

    species <- c("ecoli", "human", "corn")
    species

Existen funciones dedicadas para interaccionar con vectores, como por ejemplo la función lenght(), que nos permite conocer el número de objetos que contiene un vector. 

    length(glengths)
    length(species)

Lo que debería entregarle como resultado lo siguiente 

    [1] 3
    [1] 3

 
Tambiénn existe la función class() que entrega como resultado el tipo de data que contiene el vector, por ejemplo, ingrese lo siguiente a su consola: 

    class(glengths)
    class(species)

Lo que debería entregarle como resultado lo siguiente 

    [1] "numeric"
    [1] "character"


y finalmente la función str() que nos da un vistazo acerca del vector con que estamos trabajando. 

    str(glengths)
    str(species)
    
Lo que debería entregarle como resultado lo siguiente 

    num [1:3] 4.6  30000.0  500000.0 
    chr [1:3] "ecoli" "human" "corn"

Y para finalizar es necesario remarcar que la data que fue agregada a estos vectores se hizo anteponiendo la letra c antes de la data a agregar, la data puede ser agregada al inicio o final de un vector. 


    lengths <- c(glengths, 90) # agregando 90 al final 
    lengths <- c(30, glengths) # agregando 30 al principio 
    lengths

En esta pequeña introducción acabamos de ver 2 de los 6 tipos de data que R usa:  "carácteres" y "numeros". 
Los otros 4 son:
-."lógicos" Para TRUE y FALSE (data de tipo booleano)

-."integer" Para números enteros  (ejemplo 2L, la L le indica a R que es interger, o en español entero

-."complejo" Para representar un número real con partes imaginarias (ejemplo 1+4i

-."raw" No hay mucho que decir 

y también vimos 1 de las muchas estructuras de datos que R usa, que son los vectores, otras importantes son:

-.Las listas (list)

-.Las matrices(matrix)

-.Los data frames (data.frame) 

-.Los Factores (factor).

####Data.frames

Para terminar esta introducción entederemos como trabajar con estructuras de datos tipo data.frame, para ello es necesario descargar 
el archivo .csv del siguiente [link](http://www.datacarpentry.org/R-genomics/data/Ecoli_metadata.csv)

Para importar esta tabla a nuestra interfaz de trabajo clickeamos en el botón de "import dataset" de nuestra pestaña de "global envirnment"  o ingresamos el siguiente comando en la consola si descargamos nuestro en un nuestro directorio de trabajo (para conocer tu directorio de trabajo ingresa getwd() a la consola y para configurar uno nuevo ingresa setwd() ingresando como argumento el nuevo directorio de trabajo).

    metadata <- read.csv('Ecoli_metadata.csv')

Este contiene información acerca de una población de Escherichia coli (designada Ara-3), la cual fue cultivada por más de 40.000 generaciones en un medio mínimo limitado en glucosa, este medio estaba suplementado con citrato, el cual E. coli no puede metabolizar bajo las condiciones en que el experimento fue llevado a cabo. La población fue secuenciada a intervalos regulares, la información obtenida reveló que mutantes metabolizadores de citrato aparecieron espontaneamente cerca de la generación 31.0000. Esta metada describe la información de los clones de Ara-3 y los columnas representan  
sample: nombre del clon 
generation generación cuando la muestra fue tomada
clade 	clado basado en una arbol basado en parsimonia 
strain 	ancestral strain
cit 	citrate-using mutant status
run 	archivo de la secuencia de los reads con el id de la muestra correspondiente 
genome_size 	El tamaño del genoma en Mbp

Podemos verificar las primeras 6 lineas de nuestro data.frame con la función head(), ingrese lo siguiente a su consola: 

    head(metadata)

Pero ¿Que son concretamente los data.frames?

Los data.frame son la estructura de datos de facto para la mayoría de la data tabulada y es la estructura de dato utilizada para hacer estadistica o graficar. 

Un data.frame es una colección de vectores de largo identico, cada vector representa una columna y cada vector puede contener data de diferentes tipos. La función str() descrita anteriormente es muy util para determinar el tipo de data de cada columna.

un data.frame puede ser creado por las funciones read.csv() o read.table(). Por defecto estos convierten las columnas que contienen texto en data de tipo factor, depnediendo en lo que se desee hacer con la data conservar dicho texto como carácteres puede ser deseable, para hacerlo se debe agregar el argumento stringsAsFactors=FALSE a las funciones read.csv() o read.table().

¿y que son los factores?

Los factores son usados para categorizar datos. Los factores pueden estar ordenados o desordenados y son una clase de dsto muy importante para el análisis estadistico y la confección de gráficos. Los factores son guardados como interfers, y tiene etiquetas asociadas con estos intergers únicos, por lo que mientras que los factores se ven y comportan como vectores son realmente intergers(enteros) y hay que ser precavido de no tratarlos como carácteres.

## 2
##Laboratorio 1: Análisis de secuencias mediante Bioconductor 

Introducción
Bioconductor permite el análisis y la comprensión de data genómica generada a partir de HTS. 
Para ello cuenta con una gran variedad de paquetes que permiten trabajar con dichos archivos, importando, 
manipulando y analizando archivos fasta, fastq, BAM, gtf, bed, y archivos wig, entre otros. 
Los paquetes de Bioconductor que evaluaremos en este primer laboratorio serán los siguientes:
-IRanges 
-GenomicRanges 
-Biostrings
-AnnotationHub
-Rsamtools

Los cuales una vez instalados serán posteriormente utilizados en un ejercicio de ejemplo.  

IRanges 
El paquete IRanges permite almacenar, organizar secuencialmente y organizar 
rangos de datos de tipo interger como RLE (Run-Length Encoding).  

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("IRanges")

Para más información 

    browseVignettes("IRanges")

GenomicRanges

Representar y Manipular anotaciones y alineamientos genómicos es central para analizar data generada por HTS.
El paquete GenomicRanges define contenedores multiproposito para almacenar y manipular intervalos y variables 
definidos dentro de un genoma y contenedores más especializados para representar y manipular alineamientos cortos
contra genomas de referencia. Uno de los atributos caracteristico de este paquete es el objeto GRanges el cual 
representa un vector que contiene el nombre de la secuencia, el rango, y la hebra dentro del genoma, además de la 
opción de poder agregar metadata al vector.

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("GenomicRanges")

Para más información 

    browseVignettes("GenomicRanges")


BioString 
El paquete Biostring permite trabajar con contenedores eficientes en el uso de memoria de secuencias tipo string y 
algoritmos de busqueda de string entre otras utilidades. Todo con el fin de manipular de manera rápida un gran número 
de secuencias biologicas.

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("Biostrings")

Para más información 

    browseVignettes("Biostrings")

AnnotationHub 
Este paquete permite acceso web de manera centralizada a bases de datos como Ensembl para acceder a 
archivos genómicos de tipo VCF, bed y wig.
Además permite acceder a metadata de los archivos con que se trabaje como descripcioens textuales, tags 
y fechas de modificación. Los archivos son almacenados temporalmente en el caché para que puedan ser recuperados 
rápidamente si es necesario. 

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("AnnotationHub")

Para más información 

    browseVignettes("AnnotationHub")

-Rsamtools
Este paquete provee una interface a diferentes herramientas tales como  samtools, bcftools y tabix utilities. Para la manipulacipon de archivos de secuencias tipo SAM, FASTA, BCF y tabix

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("Rsamtools")

Para más información 

    browseVignettes("Rsamtools")

Ejercicio 

1. Lo primero que haremos será descargar todas las secuencias de cDNA de Homo sapiens como archivos FASTA desde Ensembl utilizando el paquete AnnotationHub, para lo primero debemos cargar el paquete y crear una variable que nos permita almacenar la informacion lo cual se hará mediante el siguiente comando en consola: 


    library(AnnotationHub)
    ah <- AnnotationHub()

2. Una vez cargado el paquete y la variable creada procederemos a la descarga mediante el siguiente comando en la consola: 


    ah2 <- query(ah, c("fasta", "homo sapiens", "Ensembl"))
    fa <- ah2[["AH18522"]]
    fa
    
3.Posteriormente abriremos el archivo descargado para recuperar las secuencias de interés junto con el largo de estas en un archivo FASTA mediante el siguiente comando en consola usando Rsamtools, cuyo paquete debe ser cargado. 

    library(Rsamtools)
    idx <- scanFaIndex(fa)
    idx
4.Finalmente la información obtenida como un objeto Granges mediante el comando getseq()
En este ejemplo utilizaremos el atributo param como un indicador de sets de DNAstring
Lo cual se hará mediante el siguiente comando en consola. 

    long <- idx[width(idx) > 82000]
    getSeq(fa, param=long)

Lo que se debe observar al final de este ejerccio es lo siguiente 

    A DNAStringSet instance of length 7
    width seq                                                                  names               
    [1] 101518 GCAGTCGTGCATTCCCAGCCTCGCCTCGGGTGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000342992
    [2]  82029 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000460472
    [3] 109224 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000589042
    [4] 104301 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000591111
    [5] 104301 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000615779
    [6]  82605 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000342175
    [7]  82404 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000359218

que corresponde a todas las entradas dentro del archivo con un largo mayor a 82000pb

## 3 
##Laboratorio 2: Diseño de partidores 

Introducción
Entre las variadas herramientas que pone a nuestra diposición Bioconductor una de las más usada es el alineamiento multiple y 
el diseño de partidores. En el presente laboratorio exploraremos distintas herramientas para alineamientos múltiples. 
Los paquetes de Bioconductor que evaluaremos en este primer laboratorio serán los siguientes:
-seqinR 
-msa 
-DECIPHER 

seqinR
SeqinR es la abreviación de "sequences in R" es un paquete que permite recuperar archivos de secuencias desde 
distintas bases de datos (GenBank, Swissprot, entre otras)   

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    install.packages("seqinr", repos="http://R-Forge.R-project.org")

La instalación de los paquetes ade4 y ape es recomendada mediante el asistente de instalación de paquetes de Rstudio
Para más información consultar el siguiente enlace 

    http://seqinr.r-forge.r-project.org/seqinr_2_0-7.pdf

MSA 
Este paquete provee una intrface unificada para Bioconductor de distintos algoritmos de alineamento tales como ClustalW, 
ClustalOmega y Muscle. Estos tres algoritmos se encuentran integrados dentro del paquete por lo cual una vez instalado no se necesita de herramientas externas. Además están complementados por una función de visualización en pantalla usando el paquete de LaTex TexShade.

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("msa")

Para más información 

    browseVignettes("msa")

DECIPHER 
Este paquete provee un set de herramientas para trabajar con secuencias biologicas, en la que destaca la función DesignPrimers
cuyo objetivo es determinar un set de partidores fowards y reverse que amplifiquen unicamente en un grupo de secuencias objetivo pero no las otras ingresadas, si dicho objetivo es imposible de cumplir la función es capaz de predecir el potencial de amplificación crusada con grupos de secuencias no objetivo.

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R

    source("https://bioconductor.org/biocLite.R")
    biocLite("DECIPHER")

Para más información 

    browseVignettes("DECIPHER")

Ejercicios
Como primer ejercicio recuperamos un grupo de secuencias mediante seqinR, para lo cual primero debemos crear la función encargada de llevarlo a cabo, para ello ingrese lo siguiente en consola:

    retrieveseqs <- function(seqnames,acnucdb) #Crea la función que utilizaremos luego 
    {myseqs <- list()                          #Crea la lista que contendrá las secuencias temporalmente
    require("seqinr")                          #Carga  
    choosebank(acnucdb)
    for (i in 1:length(seqnames))
    {
    seqname <- seqnames[i]
    print(paste("Retrieving sequence",seqname,"..."))
    code <-paste("AC=",seqname,sep="")
    entry<-query(code)                                     
    sequence <- getSequence(entry$req[[1]])               
    myseqs[[i]] <- sequence
    }
    closebank()
    return(myseqs)
    }

Luego procedemos a crear un vector que contenga los códigos UNIPROT de las secuencias que deseamos recuperar desde la base de datos swissprot, las secuencias de estas se almacenarán en la variables seqs. 

    seqnames <- c("P06747", "P0C569", "O56773", "Q5VKP1")  
    seqs <- retrieveseqs(seqnames,"swissprot")             

Posteriormente creamos un archivo que contenga la información descargada mediante la función write.fasta() para ello ingresamos el siguiente comando a nnuestra consola de Rstudio

    write.fasta(seqs, seqnames, file="phosphoproteins.fasta")

Se creará entonces un archivo llamado phosphoproteins.fasta en nuestra carpeta de "Documentos", con este archivo pasaremos a realizar nuestro alineamiento multiple mediante Clustalw2 y MUSCLE



	
## 4 
##Laboratorio 3: Ensamble de Genomas 

En este práctico Usted va a recibir un set de datos genómicos correspondientes a un genoma bacteriano. Debe "limpiar" las reads, ensamblarlas, comparar los resultados de ese ensamble, y finalmente anotar y visualizar. 
Etapas en el práctico:  
- Descargar reads  [aquí](https://www.dropbox.com/s/qmtja3ollqbqcml/reads.zip?dl=0) (1.4 GB)
- Realizar control de calidad --> cortar extremos 3´ de baja calidad, eliminar reads con N´s, eliminar reads cuyo puntaje de calidad promedio sea menor a cierto umbral, etc. Para lo cual se usará [PrinSeq](http://prinseq.sourceforge.net).  
- Una vez que las reads están "limpias", puede proceder con el ensamblaje. Para lo cual usará dos herramientas.
[SPAdes](http://spades.bioinf.spbau.ru) 
[MaSurCa](http://www.genome.umd.edu/masurca.html)  
- El siguiente paso es comparar los ensamblajes producidos por ambos programas. Para lo cual utilizará [QUAST](http://quast.bioinf.spbau.ru)  
- Finalmente, la anotación genómica es lo que le va a dar sentido a esto al definir dónde están los genes, qué funciones codifican y cómo. En este caso usaremos [Prokka](https://github.com/tseemann/prokka) 

####Prinseq
Desde el link descargaremos la versión "stand alone" que no requerirá más módulos que los incluidos en el paquete base de perl, en caso de no tenerlo, ingresar lo siguiente a la consola de su terminal. 

    sudo apt-get install libjson-perl

Ya instalado perl vamos a la carpeta que contiene el archivo descargado ya descomprimido y utilizamos prinseq para visualizar los datos antes de procesarlos, para ello generamos un archivo .gd 

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1.fastq -fastq2 198D_2.fastq -graph_data 198D.gd -graph_stats ld,gc,qd,ns,pt,ts,aq,de,da,sc,dn 
    
Ya generado el archivo .gd es necesario graficarlo para visualizarlo. Para ello ingrese lo siguiente a su terminal:  

    perl ruta_script/prinseq-graphs-noPCA.pl -i 198D.gd -html_all
    
Lo cual debería generar un archivo html en la carpeta en donde ejecutó el script, el cual puede ser fácilmente visualizable con cualquier navegador web pre-instalado. al visulizarlo es fácil percatar que existen reads de tamaño inferior a 50 y en el archivo 198_2.fastq una cantidad importante de reads cuyo extremo 3´ presenta una calidad menor a 20, lo que quiere decir un error cada 1000 pares de bases, por lo cual es necesario limpiar el archivo, para ello ingresaremos lo siguiente en nuestra consola del terminal:

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1.fastq -fastq2 198D_2.fastq -min_len 50 -trim_qual_right 20 -trim_qual_window 10 -trim_qual_step 1 

Para visualizar los efectos de nuestro procesamiento debemos generar un nuevo archivo .gd para ello debemos ingresar lo siguiente a nuestro terminal. 

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1_prinseq_good_Yn2j.fastq -fastq2 198D_2_prinseq_good_git9.fastq -graph_data 198D_post.gd -graph_stats ld,gc,qd,ns,pt,ts,aq,de,da,sc,dn

Es importante hacer énfasis que los codigos que agrega prinseq a cada archivo PE y singleton varía así que debe adecuarlo para que contengan el nombre de sus archivos. Ya entendido eso y generado el archivo .gd se debe gráficar denuevo para ello ingresamos lo siguiente al terminal: 

    perl prinseq-graphs-noPCA.pl -i 198D_post.gd -html_all
    
Y lo visualizamos con nuestro navegador, si todo se ejecutó como se espera el largo mínimo de nuestros reads debe ser de 50 y no debe observarse la caída en calidad en el extremo 3´ de los reads del archivo 2 previamente observado. 

####SPAdes 

Una vez finalizado el pre-procesamiento de los reads se puede proceder al ensamble, para ello primero debemos descargar el ensamblador SPAdes desde el link entregado en su última versión correspondiente para nuestro equipo. Al momento de realizar este tutorial la versión utilizada fue SPAdes-3.9.0-Linux

Esta versión no requiere instalación, solo depende de que las dependencias necesarias se encuentren instaladas, como por ejemplo Python en una versión compatible con el script de SPAdes. 

Para utilizar el ensamblador SPAdes, ingrese a la carpeta que contiene los datos pre-procesados a ingrese el siguiente comando a su terminal: 

    python ruta_script/SPAdes-3.9.0-Linux/bin/spades.py --pe1-1 198D_1_prinseq_good_Yn2j.fastq --pe1-2 198D_2_prinseq_good_git9.fastq --s1 198D_1_prinseq_good_singletons_YOxe.fastq --s2 198D_2_prinseq_good_singletons_xRRl.fastq --careful -k21,33,55,77,93 -t 2 -o .


####MaSuRCA

Con el fin de llevar a cabo un análisis comparativo de los ensambles utilizaremos también el ensamblador MaSuRCA, una vez descargado y descomprimido el archivo correspondiente procedemos ingresar a la carpeta bin y a crear un archivo llamado configuration.txt que contenga lo siguiente: 

    ####example configuration file 
    DATA
    ####PE= pe 180 20  /FULL_PATH/frag_1.fastq  /FULL_PATH/frag_2.fastq
    PE= pe 221.22 36.38  /home/fagolab/Descargas/ensamble/198D_1.fastq  /home/fagolab/Descargas/ensamble/198D_2.fastq
    PE = s1 217.23 51.00 /home/fagolab/Descargas/ensamble/198D_1_prinseq_good_singletons_YOxe.fastq
    PE = s2 185.52 56.33 /home/fagolab/Descargas/ensamble/198D_2_prinseq_good_singletons_xRRl.fastq
    END

    PARAMETERS
    GRAPH_KMER_SIZE = auto
    USE_LINKING_MATES = 1
    LIMIT_JUMP_COVERAGE = 300
    CA_PARAMETERS = cgwErrorRate=0.15 ovlMemory=4GB
    KMER_COUNT_THRESHOLD = 1
    NUM_THREADS = 8
    JF_SIZE = 60902526
    DO_HOMOPOLYMER_TRIM = 0
    END

## 5 
Laboratorio 4: Análisis de Expresión Génica

##6 
Laboratorio 5: Metagenómica

##7
Laboratorio 6: Genómica de Poblaciones
















