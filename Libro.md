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

    retrieveseqs <- function(seqnames,acnucdb) #Crea la función con dos argumentos que daremos luego 
    {myseqs <- list()                          #Crea la lista que contendrá las secuencias temporalmente
    require("seqinr")                          #Carga el paquete seqinR si es que no está cargado 
    choosebank(acnucdb)                        #Determina la base de datos a utilizar a partir del argumento dado 
    for (i in 1:length(seqnames))              #Ciclo para recorrer la lista de codigos de la secuencia a recuperar 
    {
    seqname <- seqnames[i]                     #La variable seqname toma el nombre del codigo correspondiente
    print(paste("Retrieving sequence",seqname,"...")) 
    code <-paste("AC=",seqname,sep="")         #Crea el codigo para hacer la busqueda en la base de datos    
    entry<-query(code)                         #Hace la busqueda en la base de datos y guarda la entrada           
    sequence <- getSequence(entry$req[[1]])    #Extrae la secuencia de la entrada recuperada             
    myseqs[[i]] <- sequence                    #Guarda las secuencias recuperadas temporalmente
    }
    closebank()                                #Cierra el acceso a la base de datos
    return(myseqs)                             #Retorna los valores de las secuencias recuperdas 
    }

Luego procedemos a crear un vector que contenga los códigos UNIPROT de las secuencias que deseamos recuperar desde la base de datos swissprot, las secuencias almacenadas en myseqs se almacenarán en la variables seqs. 

    seqnames <- c("P06747", "P0C569", "O56773", "Q5VKP1")  
    seqs <- retrieveseqs(seqnames,"swissprot")             

Posteriormente creamos un archivo que contenga la información descargada mediante la función write.fasta() para ello ingresamos el siguiente comando a nnuestra consola de Rstudio

    write.fasta(seqs, seqnames, file="phosphoproteins.fasta")

Se creará entonces un archivo llamado phosphoproteins.fasta en nuestra carpeta que tengamos designada como directorio de trabajo, con este archivo pasaremos a realizar nuestro alineamiento multiple mediante Clustalw2 y MUSCLE, no obstante antes de llevar a cabo dicho ejercicio es necesario recomendar un visualizador liviano llamado Aliview(Alignement Viewer) que trae integrado consigo MUSCLE, para ello debemos descargar el archivo.SH del siguiente [link](http://www.ormbunkar.se/aliview/downloads/linux/linux-version-1.18/aliview.install.run) vaya a la carpeta de descarga, abra un terminal e ingrese el siguiente comando en ella: 

    chmod 777 aliview.install.run
    sudo ./aliview.install.run 

Esto debería instalar Aliview, de lo contrario instale las dependencias que faltan (JAVA) y vuelva a intentar.
Una vez instalado Aliview y Muscle abra una terminal en la carpeta que contiene los archivos a alinear e ingrese lo siguiente en ella: 

    muscle -in proteins.fasta -out output.fasta
    aliview output.fasta

Lo que debería desplegar lo siguiente en su pantalla 

Esto debería desplegar la siguiente imagen su pantalla
![Image of Figura 2](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Aliview_imagen.jpg)

Por otra parte, para instalar ClustalW descargue el archivo correspondiente desde este [link](http://www.clustal.org/download/current/clustalw-2.1-linux-x86_64-libcppstatic.tar.gz), tras descomprimirlo ingrese a la carpeta ejecute lo siguiente en su consola de comando 

    ./clustalw2
    1
    nombredearchivo de las secuencias recuperdadas 
    2
    9
    4
    RETURN 
    1

y luego de darle nombre a los archivos de salida, copie el archivo .phy (proteinas.phy en nuestro caso) en su directorio de trabajo de R y vuelva a Rstudio, ingrese el siguiente comando en su interfaz. 

    virusaln  <- read.alignment(file = "proteinas.phy", format = "phylip")
    
Con lo cual acabamos de importar nuestro alineamiento a R mediante la función read.alingment(), una vez dentro se pueden ejecutar distintas funciones de visualización como de análisis, una de las más importantes es dist.alignment() que calcula la distancia entre cada una de las secuencias alineadas. Como ejemplo, ingrese lo siguiente a su consola de Rstudio: 

    virusdist <- dist.alignment(virusaln)  
    virusdist

Debería obtener lo siguiente: 

                 P0C569     O56773     P06747    
     O56773      0.4142670                      
     P06747      0.4678196  0.4714045           
     Q5VKP1      0.4828127  0.5067117  0.5034130

Y eso concluye nuestra introducción a alineamiento multiple y Rstudio. 

Para finalizar este laboratorio daremos una pequeña introducción de DECIPHER, el cual, si todas las instrucciones se han ejecutado exitosamente debería estar instalado y puede ser cargado en Rstudio mediante la pestaña de paquetes en la esquina inferior derecha. Tras cargarlo, creamos una variable con contenga la ruta al archivo de prueba Streptomyces_ITS_aligned.fas del paquete DECIPHER, en nuestro caso fue desde /home/usuario/R/x86_64-pc-linux-gnu-library/3.3/DECIPHER/extdata con el siguiente comando en la consola de Rstudio: 

    "/home/fagolab/Streptomyces_ITS_aligned.fas"->fas
    
Una vez cargado se procede a generar la base datos, por lo cual debemos indicar una ruta para ella o indicar que se creará en memoría, para ello ingresamos el siguiente comando: 

    dbConn <- dbConnect(SQLite(), ":memory:")

Para indicar que crearemos la base de datos en memoría y finalmente la creamos a través del siguiente comando: 

    Seqs2DB(fas, "FASTA", dbConn, "Streptomyces")

Que debería entregar como resultado la siguiente salida en consola: 

    Reading FASTA file chunk 1

    88 total sequences in table Seqs.
    Time difference of 0.18 secs

Una vez creada la base de datos procedemos a generar los grupos y parsear los identificadores de cada secuencia de la base de datos para identificar más fácilmente cada grupo generado. Para ello ingresamos lo siguiente en consola:  

    desc <- dbGetQuery(dbConn, "select description from Seqs")
    desc <- unlist(lapply(strsplit(desc$description, "Streptomyces ", fixed=TRUE),function(x) return(x[length(x)])))
    desc <- gsub("sp. ", "", desc, perl=TRUE)
    desc <- gsub("sp_", "", desc, perl=TRUE)
    desc <- unlist(lapply(strsplit(desc, " ", fixed=TRUE), function(x) return(x[1])))
    unique(desc)

Que debería generar la siguiente salida en su consola: 

    [1] "albus"             "clavuligerus"      "ghanaensis"        "griseoflavus"     
    [5] "lividans"          "pristinaespiralis" "Mg1"               "SPB78"            
    [9] "AA4"               "SPB74"             "SirexAA-E"         "scabiei"          
    [13] "griseus"           "coelicolor"        "cattleya"          "bingchenggensis"  
    [17] "avermitilis"       "C"                 "Tu6071"           

Y una vez obtenidos los nombres de las especies procedemos a agregarlos a la base de datos, lo cual debería entregar una salida automática como la indicada: 

    Add2DB(data.frame(identifier=desc), dbConn)

    Expression:
    update or replace Seqs set identifier = :identifier where row_names = :row_names

    Added to table Seqs:  "identifier".
    Time difference of 0.01 secs

Para generar los primers grupo espécificos primero debemos generar k-mers conocidos como "tiles" para ello ingresamos el siguiente comando: 

    tiles <- TileSeqs(dbConn, add2tbl="Tiles", minCoverage=1)


Luego generar todos los primers posibles para entre ellos seleccionar aquellos que nos permitan identificar nuestro grupo de interés (Avermitilis) de los demás.

    primers <- DesignPrimers(tiles, identifier="avermitilis",minCoverage=1, minGroupCoverage=1)
    
Luego indicamos al programa encontrar la mejor combinación de primers Forward y Reverse para nuestro grupo objetivo.

    primers <- DesignPrimers(tiles, identifier="avermitilis", minCoverage=1,minGroupCoverage=1, numPrimerSets=5, maxSearchSize=20)

Ahora cada fila de la variable primers contiene solo un par de primers foward y reverse, si visualizamos el out mediante la siguiente linea de comando en nuestra consola de Rstudio: 

    head(primers)
    
Deberìamos observar que cada pareja de partidores solo amplifica S. avermitilis y ninguna otra especie, como queda de manifiesto dado que la columna de mismatches està vacía.

    identifier start_forward start_reverse product_size start_aligned_forward
    1 avermitilis           245           326           82                   247
    2 avermitilis           249           326           78                   248
    3 avermitilis           245           325           81                   247
    4 avermitilis           249           325           77                   248
    5 avermitilis           245           328           84                   247
    start_aligned_reverse permutations_forward permutations_reverse score_forward
    1                   351                    1                    1             0
    2                   351                    1                    1             0
    3                   350                    1                    1             0
    4                   350                    1                    1             0
    5                   353                    1                    1             0
    score_reverse score_set         forward_primer.1 forward_primer.2
    1  -3.64000....         0 CGTTGATTATTCGGCACACTCGAC             <NA>
    2  -3.64000....         0    GATTATTCGGCACACTCGACC             <NA>
    3  -4.06252....         0 CGTTGATTATTCGGCACACTCGAC             <NA>
    4  -4.06252....         0    GATTATTCGGCACACTCGACC             <NA>
    5  -0.00036....         0 CGTTGATTATTCGGCACACTCGAC             <NA>
    forward_primer.3 forward_primer.4  reverse_primer.1 reverse_primer.2
    1             <NA>             <NA> ACCCTCGCCCTCCCATG             <NA>
    2             <NA>             <NA> ACCCTCGCCCTCCCATG             <NA>
    3             <NA>             <NA> CCCTCGCCCTCCCATGT             <NA>
    4             <NA>             <NA> CCCTCGCCCTCCCATGT             <NA>
    5             <NA>             <NA> ACACCCTCGCCCTCCCA             <NA>
    reverse_primer.3 reverse_primer.4 forward_efficiency.1 forward_efficiency.2
    1             <NA>             <NA>         0.954290....                   NA
    2             <NA>             <NA>         0.815524....                   NA
    3             <NA>             <NA>         0.954290....                   NA
    4             <NA>             <NA>         0.815524....                   NA
    5             <NA>             <NA>         0.954290....                   NA
    forward_efficiency.3 forward_efficiency.4 reverse_efficiency.1
    1                   NA                   NA         0.944266....
    2                   NA                   NA         0.944266....
    3                   NA                   NA         0.925497....
    4                   NA                   NA         0.925497....
    5                   NA                   NA         0.969813....
    reverse_efficiency.2 reverse_efficiency.3 reverse_efficiency.4
    1                   NA                   NA                   NA
    2                   NA                   NA                   NA
    3                   NA                   NA                   NA
    4                   NA                   NA                   NA
    5                   NA                   NA                   NA
    7
    forward_coverage.1 forward_coverage.2 forward_coverage.3 forward_coverage.4
    1                  1                 NA                 NA                 NA
    2                  1                 NA                 NA                 NA
    3                  1                 NA                 NA                 NA
    4                  1                 NA                 NA                 NA
    5                  1                 NA                 NA                 NA
    reverse_coverage.1 reverse_coverage.2 reverse_coverage.3 reverse_coverage.4
    1                  1                 NA                 NA                 NA
    2                  1                 NA                 NA                 NA
    3                  1                 NA                 NA                 NA
    4                  1                 NA                 NA                 NA
    5                  1                 NA                 NA                 NA
    mismatches_forward mismatches_reverse mismatches_set
    1
    2
    3
    4
    5
 
¡Hemos logrado generar nuestra pareja de partidores grupo especifico!

## 4 
##Laboratorio 3: Ensamble de Genomas 

En este práctico Usted va a recibir un set de datos genómicos correspondientes a un genoma bacteriano. Debe "limpiar" las reads, ensamblarlas, comparar los resultados de ese ensamble, y finalmente anotar y visualizar. 
Etapas en el práctico:  
- Descargar reads  [aquí](https://www.dropbox.com/s/qmtja3ollqbqcml/reads.zip?dl=0) (1.4 GB)
- Realizar control de calidad --> cortar extremos 3´ de baja calidad, eliminar reads con N´s, eliminar reads cuyo puntaje de calidad promedio sea menor a cierto umbral, etc. Para lo cual se usará [PrinSeq](http://prinseq.sourceforge.net).  
- Una vez que las reads están "limpias", puede proceder con el ensamblaje. Para lo cual usará dos herramientas.
[SPAdes](http://spades.bioinf.spbau.ru) 
[MaSurCa](http://www.genome.umd.edu/masurca.html)  
- Para determinar a que organismo corresponden los ensambles generados usaremos la herramienta [MLST](https://github.com/tseemann/mlst) con el fin de determinar si existe un genoma de referencia para el siguiente paso. 
- El siguiente paso consiste en comparar los ensamblajes producidos por ambos programas. Para lo cual utilizará [QUAST](http://quast.bioinf.spbau.ru)  
- Finalmente, la anotación genómica es lo que le va a dar sentido a esto al definir dónde están los genes, qué funciones codifican y cómo. En este caso usaremos [Prokka](https://github.com/tseemann/prokka) 

####Prinseq
Desde el link descargaremos la versión "stand alone" que no requerirá más módulos que los incluidos en el paquete base de perl, en caso de no tenerlo, ingresar lo siguiente a la consola de su terminal. 

    sudo apt-get install libjson-perl

Ya instalado perl vamos a la carpeta que contiene los archivos con las secuencias ya descargados y descomprimidos y utilizamos prinseq para visualizar los datos antes de procesarlos, para ello generamos un archivo .gd abriendo un terminal en la misma carpeta e ingresando el siguiente comando:

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1.fastq -fastq2 198D_2.fastq -graph_data 198D.gd -graph_stats ld,gc,qd,ns,pt,ts,aq,de,da,sc,dn 
    
Ya generado el archivo .gd es necesario graficarlo para visualizarlo. Para ello ingrese lo siguiente a su terminal:  

    perl ruta_script/prinseq-graphs-noPCA.pl -i 198D.gd -html_all

Lo cual debería generar un archivo html en la carpeta en donde ejecutó el script, el cual puede ser fácilmente visualizable con cualquier navegador web pre-instalado, visualice el archivo html generado.

Los primeros gráficos que nos reportará prinseq corresponden a un gráfico de columna de la distribución de largo de los reads en los archivos de salida del secuenciador, en donde el eje X representará el tamaño del read y el eje Y la cantidad de reads con dicho tamaño, junto con una pequeña estadistica. 
![Image of Figura 4](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Prinseq_L1.jpg)

De esta imagen, en lo que debemos centrar nuestra atención, además de las muy diferentes tendencias entre los archivos 1 y 2, siendo la del archivo 1 claramente de mayor calidad, es que para ambos archivos se reporta un largo mínimo de read de 35 pares de bases, para evitar que SPADES cometa errores con reads tan pequeños será necesario eliminarnos de nuestros archivos al momento de "limpiarlos".  

Luego tenemos un gráfico del puntaje de calidad para cada posición de todos los reads expresados en un boxplot para el archivo 1 donde se puede pareciar que algunos reads en su extremo 3´ contienen nucleotidos de baja calidad (menor a 20). pero que la gran mayoría de los reads de acuerdo al gráfico de columna inmediatamente luego de este muestra que en promedio la mayoría de los reads son de buena calidad, dado el desplazamiento hacia la derecha mostrado por la campana de dicho gráfico.  
![Image of Figura 5](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Prinseq_L2.jpg)

Por otro lado el gráfico del puntaje de calidad para el archivo 2 debería llamarnos la atención, ya que un proporción importante de los nucleótidos que componen los reads de este archivo tienen un puntaje de calidad bajo, así como lo muestra la campana de distribución asociada a esta figura. 

![Image of Figura 3](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Prinseq_pre.jpg)

Una calidad menor a 20, quiere decir un error cada 100 pares de bases, por lo cual es necesario limpiar el archivo, para ello y tomando en consideración el tamaño de los reads ingresaremos lo siguiente en nuestra consola del terminal:

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1.fastq -fastq2 198D_2.fastq -min_len 50 -trim_qual_right 20 -trim_qual_window 10 -trim_qual_step 1 

Para visualizar los efectos de nuestro procesamiento debemos generar un nuevo archivo .gd para ello debemos ingresar lo siguiente a nuestro terminal. 

    perl ruta_script/prinseq-lite.pl -verbose -fastq 198D_1_prinseq_good_Yn2j.fastq -fastq2 198D_2_prinseq_good_git9.fastq -graph_data 198D_post.gd -graph_stats ld,gc,qd,ns,pt,ts,aq,de,da,sc,dn

Es importante hacer énfasis que los codigos que agrega prinseq a cada archivo PE y singleton varía así que debe adecuarlo para que contengan el nombre de sus archivos. Ya entendido eso y generado el archivo .gd se debe gráficar denuevo para ello ingresamos lo siguiente al terminal: 

    perl prinseq-graphs-noPCA.pl -i 198D_post.gd -html_all
    
Y lo visualizamos con nuestro navegador, si todo se ejecutó como se espera el largo mínimo de nuestros reads debe ser de 50 y no debe observarse la caída en calidad en el extremo 3´ de los reads del archivo 2 previamente observado, en una imagen similar a esta: 

![Image of Figura 4](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Prinseq_post.jpg)


####SPAdes 

Una vez finalizado el pre-procesamiento de los reads se puede proceder al ensamble, para ello primero debemos descargar el ensamblador SPAdes desde el link entregado en su última versión correspondiente para nuestro equipo. Al momento de realizar este tutorial la versión utilizada fue SPAdes-3.9.0-Linux

Esta versión no requiere instalación, solo depende de que las dependencias necesarias se encuentren instaladas, como por ejemplo Python en una versión compatible con el script de SPAdes. 

Para utilizar el ensamblador SPAdes, ingrese a la carpeta que contiene los datos pre-procesados a ingrese el siguiente comando a su terminal: 

    python ruta_script/SPAdes-3.9.0-Linux/bin/spades.py --pe1-1 198D_1_prinseq_good_Yn2j.fastq --pe1-2 198D_2_prinseq_good_git9.fastq --s1 198D_1_prinseq_good_singletons_YOxe.fastq --s2 198D_2_prinseq_good_singletons_xRRl.fastq --careful -k21,33,55,77,93 -t 2 -o .

El cual una vez termine de correr debería entregar una carpeta en el directorio desde donde se ejecutó que contenga los siguientes archivos: 

    assembly_graph.fastg  input_dataset.yaml  misc                spades.log
    before_rr.fasta       K21                 mismatch_corrector  tmp
    contigs.fasta         K33                 params.txt          warnings.log
    contigs.paths         K55                 quast_test_output
    corrected             K77                 scaffolds.fasta
    dataset.info          K93                 scaffolds.paths

De esta lista de archivos el que debe interesarnos más es el scaffolds.fasta, el cual corresponde a una sobrelapamiento de contigs (que a su vez son un sobrelapamiento de los reads) pero a diferencia de a estos últimos organizados y separados por gaps de largo conocido. 

####MaSuRCA

Con el fin de llevar a cabo un análisis comparativo de los ensambles utilizaremos también el ensamblador MaSuRCA, una vez descargado y descomprimido el archivo correspondiente, debemos descargar tambièn el programa [Jellyfish](https://github.com/gmarcais/Jellyfish/releases/download/v2.2.6/jellyfish-2.2.6.tar.gz) el cual es necesario para hacer funcionar el ensamblador MaSurCA, para ello una vez descomprimido, movemos la carpeta resultante al directorio en donde tengamos guardados nuestros demás programas, entramos a la carpeta ya movida y abrimos un terminal donde debemos ingresar el siguiente comando: 

    ./configure
    make
    sudo make install

Una vez realizado esto procedemos ingresamos a la carpeta bin y copiamos el archivo jellyfish.bin a la carpeta donde tengamos almacenados los datos fastq descargados y abrimos una terminal, en la cual debemos ingresar el siguiente comando: 

    /ruta_completa_MaSuRCA/bin/masurca -g configuration.txt

Al ingresar al archivo creado con cualquier editor de texto deberìa observar algo como esto: 

    # example configuration file 
    # DATA is specified as type {PE,JUMP,OTHER} and 5 fields:
    # 1)two_letter_prefix 2)mean 3)stdev 4)fastq(.gz)_fwd_reads
    # 5)fastq(.gz)_rev_reads. The PE reads are always assumed to be
    # innies, i.e. --->.<---, and JUMP are assumed to be outties
    # <---.--->. If there are any jump libraries that are innies, such as
    # longjump, specify them as JUMP and specify NEGATIVE mean. Reverse reads
    # are optional for PE libraries and mandatory for JUMP libraries. Any
    # OTHER sequence data (454, Sanger, Ion torrent, etc) must be first
    # converted into Celera Assembler compatible .frg files (see
    # http://wgs-assembler.sourceforge.com)
    DATA
    PE= pe 180 20  /FULL_PATH/frag_1.fastq  /FULL_PATH/frag_2.fastq
    JUMP= sh 3600 200  /FULL_PATH/short_1.fastq  /FULL_PATH/short_2.fastq
    OTHER=/FULL_PATH/file.frg
    END
    PARAMETERS
    #this is k-mer size for deBruijn graph values between 25 and 101 are supported, auto will compute the optimal size based on the read data and GC content
    GRAPH_KMER_SIZE = auto
    #set this to 1 for Illumina-only assemblies and to 0 if you have 1x or more long (Sanger, 454) reads, you can also set this to 0 for large data sets with high jumping clone coverage, e.g. >50x
    USE_LINKING_MATES = 0
    #this parameter is useful if you have too many jumping library mates. Typically set it to 60 for bacteria and 300 for the other organisms 
    LIMIT_JUMP_COVERAGE = 300
    #these are the additional parameters to Celera Assembler.  do not worry about performance, number or processors or batch sizes -- these are computed automatically. 
    #set cgwErrorRate=0.25 for bacteria and 0.1<=cgwErrorRate<=0.15 for other organisms.
    CA_PARAMETERS = cgwErrorRate=0.15 ovlMemory=4GB
    #minimum count k-mers used in error correction 1 means all k-mers are used.  one can increase to 2 if coverage >100
    KMER_COUNT_THRESHOLD = 1
    #auto-detected number of cpus to use
    NUM_THREADS = 16
    #this is mandatory jellyfish hash size -- a safe value is estimated_genome_size*estimated_coverage
    JF_SIZE = 200000000
    #this specifies if we do (1) or do not (0) want to trim long runs of homopolymers (e.g. GGGGGGGG) from 3' read ends, use it for high GC genomes
    DO_HOMOPOLYMER_TRIM = 0
    END

En este archivo debemos agregar un gato(#) al comienzo de todas las lineas entre DATA y END y agregar la siguiente linea:

    PE= pe 221.22 36.38  /ruta_completa/198D_1.fastq  /ruta_completa/198D_2.fastq
    
y cambiar el valor de NUM_THREADS al entre 25% y 50% de los procesadores de su PC. Una vez realizado esto abra una terminal e ingrese los siguientes comandos: 

    /ruta_completa_MaSuRCA/bin/masurca configuration.txt
    ./assemble.sh

Si todo funcionó correctamente los resultados de su ensamble (contigs y scaffolds) se encuentran dentro de la carpeta en que ejectó la anterior linea de comando en la siguiente ruta y con lo siguientes nombres:

    CA/10-gapclose/genome.ctg.fasta
    CA/10-gapclose/genome.scf.fasta
    
####MLST
La instalación de MLST es algo distinta a la de los programas anteriores, para ello debemos tener instalado primero Git en nuestro ordenador, lo cual además permite trabajar de manera más expedita con GitHub, para ello abrimos un terminal e ingrsamos la siguiente linea de comando: 

    sudo apt-get update
    sudo apt-get install git

Posterior a esto debemos instalar otras dependencias que son necesarios para el funcionamiento de MLST para ello ingresamos las siguientes lineas de comando a nuestro terminal: 

    sudo apt-get install libmoo-perl liblist-moreutils-perl
    sudo apt-get install ncbi-blast+
    
Una vez instalado Git y las depdencias procedemos a abrir una terminal en la carpeta donde deseamos que esté instalado MLST, luego ingresamos la siguiente linea de comando: 

    git clone https://github.com/tseemann/mlst.git
    ls mlst

Lo cual debería entregar un output como el siguiente: 

    bin  db  LICENSE  perl5  README.md  scripts

Si todo ha funcionado correctamente deberìamos ser capaces de ingresar a la carpeta que contiene el ensamble de SPADES (scaffolds) y ejecutar la siguientel linea de comando:

    /ruta_completa_script/bin/mlst nombre_scaffold.fasta
    
Lo cual deberìa entregar un output como el siguiente: 

    scaffolds.fasta	pfluorescens	-	glnS(-)	gyrB(-)	ileS(~75)	nuoD(~75)	recA(72?)	rpoB(~67)	rpoD(~64)

Siendo nuestra especie en cuestión Pseudomona fluorescens, cuyo genoma de referencia puede descargarse de [aquì](http://www.ncbi.nlm.nih.gov/nuccore/CP003150.1) 

Este archivo .fasta será muy importante al momento de realizar la comparación de los ensambles con QUAST 


####Quast
Al igual que prinseq la instalación para ejecutar QUAST es muy sencilla, ademàs de descargar y descomprimir el archivo que contiene la última versión del software desde el link dado previamente, se deben descargar ciertos paquetes para que el programa funcione correctamente, estos son un compilador de Java (javac) y la libreria matplotlib de Python.
para ello abra su terminal e ingrese las siguientes lineas de comando: 

    sudo apt-get install python-matplotlib
    sudo apt-get install javac

Luego colocar la carpeta descomprimida de Quast en el directorio de su elección, ingresar a la carpeta, abrir una terminal e ingresar la siguiente linea de comando: 

    python quast.py --test
    
Lo cual deberìa entregarle un output bastante grande pero que finalice con: 

    Thank you for using QUAST!

    TEST PASSED!


Tras lo cual podemos colocar los ensambles generados por SPADES y MaSuRCA en una misma carpeta, abrir la terminal y ejecutar el siguiente comando.

    /ruta_completa/quast.py -o . ensamble_SPADES.fasta \ ensamble_MaSuRCA.fasta \ -R genoma_referencia.fasta  

Lo cual debería generar una carpeta en la carpeta actual que contenga los siguientes archivos.  

    basic_stats     quast.log    report.tsv             transposed_report.tsv
    icarus.html     report.html  report.txt             transposed_report.txt
    icarus_viewers  report.pdf   scaffolds.fasta
    report.tex   transposed_report.tex

Siendo el archivo report.pdf el que más nos interesa. 

####Prokka 
La instalación de prokka es algo distinta a la de los programas anteriores, para ello debemos tener instalado primero Git en nuestro ordenador, lo cual además permite trabajar de manera más expedita con GitHub, para ello abrimos un terminal e ingrdamos la siguiente linea de comando: 

    sudo apt-get update
    sudo apt-get install git

Posterior a esto debemos instalar otras dependencias que son necesarios para el funcionamiento de prokka para ello ingresamos la siguiente linea de comando a nuestro terminal: 

    sudo apt-get install libdatetime-perl libxml-simple-perl libdigest-md5-perl bioperl

Una vez instalado Git y las depdencias procedemos a abrir una terminal en la carpeta donde deseamos que esté instalado prokka, luego ingresamos la siguiente linea de comando: 

    git clone https://github.com/tseemann/prokka.git
    ls prokka

Lo cual debería entregar un output como el siguiente: 

    bin       db   mydir    perl5      binaries  doc  README.md

Posteriormente procedemos a indexar las bases de datos que descargamos junto a prokka ingresando la siguiente linea de comando:

    prokka/bin/prokka --setupdb
 
Finalmente para comprbar que prokka esté correctamente instalado ingresamos las siguientes lineas de comando: 

    cd prokka
    bin/prokka --version
    
Lo cual debería entregar un output como el siguiente:

    prokka 1.12-beta

Por último y el objetivo de todo esto que consiste en ejecutar Prokka para que prediga y anote los genes en los ensambles que generamos, abrimos la carpeta que contiene nuestros ensambles y abrimos nuestra terminal para ingresar la siguiente linea de comando para cada uno de nuestros ensambles: 

    /ruta_completa/bin/prokka --outdir mydir --prefix mygenome_MaSuRCA_o_SPADESnombre_ensamble_MaSuRCA_o_SPADES.fasta
    
Lo cual debería entregar un output como este: 

    mygenome.err  mygenome.fna  mygenome.gff  mygenome.tbl
    mygenome.faa  mygenome.fsa  mygenome.log  mygenome.txt
    mygenome.ffn  mygenome.gbk  mygenome.sqn

Siendo los archivos .gbk y .txt los que más nos importan, en particular el último al abrirlo con un editor de texto debería contener información similar a esta: 

    organism: -----
    contigs: 449
    bases: 7129801
    tRNA: 63
    tmRNA: 1
    CDS: 6423

####Artemis 
Por el momento lo más seguro es que te encuentres bastante decepcionado con el output que has obtenido tras tanto trabajo, esto es debido a que no hemos sido capaces de visualizar correctamente nuestros resultados, por lo que mediante el programa Artemis los graficaremos, para ello abra la terminal e ingrese la siguiente linea de comando: 

    sudo apt install artemis
    
Tras lo cual podremos ejecutar artemis abriendo una terminal en la carpeta mydir ( la que contiene los archivos de salida de prokka) e ingresar la siguiente linea de comando: 

    art mygenome.gff
    
La cual debería abrir la interfaz grárfica de Artemis y deberíamos ser capaces de ver algo así
![Image of Figura 6](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Artemis.jpg)

y si activa la función Open in DNAPlotter en archivos deberíamos visualizar lo siguiente:
![Image of Figura 7](https://github.com/Daniel-Tichy/Bioinfo-Geno/blob/master/Aliview_imagen2.jpg)

## 5 
Laboratorio 4: Análisis de Expresión Génica 
http://www.gettinggeneticsdone.com/2015/12/tutorial-rna-seq-differential.html
http://www.bioconductor.org/help/workflows/rnaseqGene/
http://www.nathalievilla.org/doc/pdf/tutorial-rnaseq.pdf
https://github.com/crazyhottommy/RNA-seq-analysis

##6 
Laboratorio 5: Metagenómica 
https://bioconductor.org/packages/3.3/bioc/html/phyloseq.html
https://www.dropbox.com/s/7xzfr744rig1qze/datos_lab.zip?dl=0

##7
Laboratorio 6: Genómica de Poblaciones
http://membres-timc.imag.fr/Olivier.Francois/tutoRstructure.pdf















