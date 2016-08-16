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

    usuario@nombre_del_equipo:~$ R

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
 



 


## 2
Laboratorio 1: Análisis de secuencias mediante Bioconductor 

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
Este paquete provee una interface a diferentes herramientas tales como  
samtools, bcftools y tabix utilities. Para la manipulacipon de archivos de secuencias 
tipo SAM, FASTA, BCF y tabix

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R
source("https://bioconductor.org/biocLite.R")
biocLite("Rsamtools")

Para más información 
browseVignettes("Rsamtools")

Ejercicio 

1. Lo primero que haremos será descargar todas las secuencias de cDNA de Homo sapiens como archivos FASTA desde Ensembl utilizando 
el paquete AnnotationHub, para lo primero debemos cargar el paquete y crear una variable que nos permita almacenar la informacion 
lo cual se hará mediante el siguiente comando en consola: 
library(AnnotationHub)
ah <- AnnotationHub()
2. Una vez cargado el paquete y la variable creada procederemos a la descarga mediante el siguiente comando en la consola: 
ah2 <- query(ah, c("fasta", "homo sapiens", "Ensembl"))
fa <- ah2[["AH18522"]]
fa
3.Posteriormente abriremos el archivo descargado para recuperar las secuencias de interés junto con el largo de estas en un archivo 
FASTA mediante el siguiente comando en consola usando Rsamtools, cuyo paquete debe ser cargado. 
library(Rsamtools)
idx <- scanFaIndex(fa)
idx
4.Finalmente la información obtenida como un objeto Granges mediante el comando getseq()
En este ejemplo utilizaremos el atributo param como un indicador de sets de DNAstrin
Lo cual se hará mediante el siguiente comando en consola. 
long <- idx[width(idx) > 82000]
getSeq(fa, param=long)
Lo que se debe observar al final de este ejerccio es lo siguiente 
##   A DNAStringSet instance of length 7
##      width seq                                                                  names               
## [1] 101518 GCAGTCGTGCATTCCCAGCCTCGCCTCGGGTGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000342992
## [2]  82029 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000460472
## [3] 109224 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000589042
## [4] 104301 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000591111
## [5] 104301 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000615779
## [6]  82605 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000342175
## [7]  82404 GAGCAGTCGTGCATTCCCAGCCTCGCCTCGGGT...ACAAAATAAAGCAAGCTATCTGCACCTCAAAA ENST00000359218

que corresponde a todas las entradas dentro del archivo con un largo mayor a 82000pb

## 3 
Laboratorio 2: Diseño de partidores 

Introducción
Entre las variadas herramientas que pone a nuestra diposición Bioconductor una de las más usada es el alineamiento multiple y 
el diseño de partidores. En el presente laboratorio exploraremos herramientas para alineamientos múltiples. 
Los paquetes de Bioconductor que evaluaremos en este primer laboratorio serán los siguientes:
-seqinR 
-msa 
-DECIPHER 

seqinR
SeqinR es la abreviación de "sequences in R" es un paquete que permite recuperar archivos de secuencias desde 
distintas bases de datos (GenBank, Swissprot, entre otras)   

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R
install.packages("seqinr", repos="http://R-Forge.R-project.org")

La instalación de los paquetes ade4 y ape es recomendada mediante el asistente de instalación de paquetes de Rstudio (ver imagen) 

Para más información consultar el siguiente enlace 
http://seqinr.r-forge.r-project.org/seqinr_2_0-7.pdf

Msa 
Este paquete provee una interface unificada para Bioconductor de distintos algoritmos de alineamento tales como ClustalW, 
ClustalOmega y Muscle. 
Estos tres algoritmos se encuentran integrados dentro del paquete por lo cual una vez instalado no se necesita de herramientas externas.
Estos algoritmos de alineamento multiple están complementados por una función de visualización en pantalla usando el paquete de 
LaTex TexShade.

Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R
source("https://bioconductor.org/biocLite.R")
biocLite("msa")

Para más información 
browseVignettes("msa")

DECIPHER 
Este paquete provee un set de herramientas para trabajar con secuencias biologicas, en la que destaca la función DesignPrimers
cuyo objetivo es determinar un set de partidores fowards y reverse que amplifiquen unicamente en un grupo de secuencias objetivo pero no 
en otras, si dicho objetivo es imposible de cumplir la función es capaz de predecir el potencial de amplificación crusada con grupos 
de secuencias no objetivo.  
Para instalar este paquete es necesario ingresar el siguiente comando a la consola de R
source("https://bioconductor.org/biocLite.R")
biocLite("DECIPHER")

Para más información 
browseVignettes("DECIPHER")

Ejercicio 
El Ejercicio consistirá en generar una parjea de partidores especificos para la detección de la toxina termolábil de E. coli ETEC 
1. Para o cual lo primero que debemos hacer es crear una lista que contenga los ID de las secuencias a recuperar

> retrieveseqs <- function(seqnames,acnucdb)
  {
     myseqs <- list()   # Make a list to store the sequences
     require("seqinr")  # This function requires the SeqinR R package
     choosebank(acnucdb)
     for (i in 1:length(seqnames))
     {
        seqname <- seqnames[i]
        print(paste("Retrieving sequence",seqname,"..."))
        queryname <- "query2"
        query <- paste("AC=",seqname,sep="")
        query(`queryname`,`query`)
        seq <- getSequence(query2$req[[1]]) # Makes a vector "seq" containing the sequence
        myseqs[[i]] <- seq
     }
     closebank()
     return(myseqs)
  }

> seqnames <- c("AB011677.1")  # Make a vector containing the names of the sequences
> seqs <- retrieveseqs(seqnames,"genbank")             # Retrieve the sequences and store them in list variable "seqs"
> length(seqs)                                 # Print out the number of sequences retrieved
 [1] 4
> seq1 <- seqs[[1]]                            # Get the first sequence
> seq1[1:20]                                   # Print out the first 20 letters of the first sequence
	
## 4 
Laboratorio 3: Ensamble de Genomas 

## 5 
Laboratorio 4: Análisis de Expresión Génica

##6 
Laboratorio 5: Metagenómica

##7
Laboratorio 6: Genómica de Poblaciones















