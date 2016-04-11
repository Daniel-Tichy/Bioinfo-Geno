# Prueba 01 - Bioinformática genómica
___

**Nombre: Daniel Tichy**  
**Fecha:10/04/2016**
&nbsp;

#  Identificación de Bacterias halofilas con potencial genómico para la producción de Biobutanol.

##  Introducción 

La volatilidad de los mercados, sumado a la creciente demanda por combustibles fósiles y otros químicos, así como los efectos causados en el medio ambiente debido al sobreconsumo de este tipo de recursos, han provocado un vuelco en la atención del mundo hacia fuentes de energía renovables, en especial, la biomasa(1).   
La fermentación ABE, es un proceso de fermentación antiguo utilizado para la producción de acetona, butanol y etanol. Después de la segunda guerra mundial alrededor del 60% del Butanol y el 10% de la acetona mundial se producían mediante este método(2). Pero con el advenimiento del petróleo, se privilegio la forma de producción petroquímica y actualmente no se producen estos compuestos de esta manera industrialmente. Todas las bacterias reportadas hasta hace poco que son capaces de producir naturalmente butanol pertenecían a la clase
Clostridia, las cuales se caracterizan por ser anaeróbicas estrictas que crecen relativamente lento en comparación a otras bacterias aeróbicas bien caracterizadas, lo que sumado a su baja tolerancia a presión osmótica, la común contaminación por bacteriófagos, falta de herramientas moleculares para su edición, la baja densidad celular que presenta durante la fermentación 
y a la formación indeseada de esporas llevan a que la productividad mediante este método sea baja(3).
Además la producción de un compuesto sumamente diluido significa un alto consumo de agua fresca que podría para ser usada de manera más eficiente. Por lo mismo han existido esfuerzos para utilizar sistemas heterólogos que permitan no depender de bacterias de la clase Clostridia, pero sin mucho éxito(4)(5)(6).
Por otro lado las bacterias halófilas han sido propuestas como microorganismos ventajosos para su uso en bioprocesos(7) ya que permitirían procesos no estériles y continuos utilizando agua de mar como medio(8) Reduciendo así costos y el  consumo de agua fresca. 
Durante 2011 en Irán se aisló y secuenció una cepa de Nesterenkonia sp.(9)que recientemente demostró ser capaz de llevar a cabo la fermentación ABE, demostrando así que esta vía metabólica no estaba restringida la clase Clostridia(10). 
En Chile contamos con uno de los reservorios de bacterias halofilas del mundo, el desierto de Atacama, localizado entre las latitudes 17° y 27° sur, entre sus caracteristicas destacan ser uno de los desiertos más antiguos y así como más secos, con precipitación anuales menores a 2mm(11). Hasta hace 40 años se pensaba incluso que por estas condiciones, sumado a la alta
salinidad y la radiación UV no existía vida microbiana en este lugar. No obstante durante los últimos 10 años se han descubierto Bacteria, Archaea y Eukarya que se han adaptado para sobrevivir en estas condiciones(12) Entre las que destacan las bacterias halófilas, en particular las moderadamente halófilas, constituyen un grupo diverso de microorganismos emergen 
como un arista de estudio interesante para la búsqueda de bacterias con potencial genómico uso en la producción de Biobutanol.
Es decir que posean las enzimas básicas descritas para ser capaces de llevar a cabo la fermentación ABE. 

##  Objetivo 
Identificar bacterias halófilas con potencial genómico para la producción de Biobutanol. 

##  Diseño experimental

####Toma de muestras
Durante un espacio temporal determinado (ej. Julio 2017) procederemos a recolectar muestras de agua de diferentes sitios 
de los salares Huasco, Llamara, Atacama, Capur, Carcote, Carmen, Navidad, Ollagüe, Maricunga y Las Parinas por su homogena distribución geográfica y de altitud. Al momento de recolectar la muestra se determinó la salinidad mediante la medición la conductividad a través de un medidor YSI 3100, se registró el pH con un medidor Hanna HI 8314 y realizó un registro de T° 
durante 24 horas que se comparó con los datos de variación térmica entregados por la dirección meteorológica de Chile. 
####Cultivo y aislamiento. 
Aquellas muestras que presentasen una concentración de sales mayor al 4.7 (0.8M) y menor al 20% (3.4M), serán cultivadas en cinco medios comunes para crecimiento de bacterias halofilas moderadas(13) ajustando el pH y aplicando una determinada temperatura de cultivo en relación a los valores obtenidos al momento de recolectar la muestra, todo con el fin de aislar colonias fenotípicamente distintas. 
####
Posteriormente para determinar el potencial de las bacterias aisladas para la producción de biobutanol se ocupará como indicador la tolerancia a este solvente, para ello se les someterá a un desafío de butanol cultivandolas en 50 ml de medio TB hasta un OD600 de 1.5 a la temperatura determinada previamente con 250rpm de agitación. 
Una vez alcanzada dicha absorbancia se procederá a someter a los cultivos a una concentraciones de entre 0% a 2% (peso/volumen)de butanol durante 24 horas, cada 3 horas se tomara una muestra de 1ml, la cual se diluirá en medio TB 1:10, se centrifugará a 5000rpm por 30 minutos y se eliminará el sobrenandante para eliminar el butanol, las bacterias serán recuperadas resuspendiendo el pellet 
obtenido en 10 ml de buffer fosfato a pH 7.0 y se determinarán la concentración (CFU/ml) mediante un ensayo en placa  aplicando 
las condieraciones de cultivo determinadas previamente para cada bacteria. Posteriormente aquellas bacterias que hayan presentado una alta resistencia a butanol (disminución en concentración no menor a un orden de magnitud con respecto al control de 0%) 
####Secuenciación de genoma completo (WGS)
Una vez aisladas realizaremos una secuenciación de genoma completo a cada bacteria aislada.
De acuerdo a lo descrito en el protocolo ya publicado(14). Para ellos extraeremos el DNA genómica mediante kits de extracción Genetra Puregene Yeast/Bact. kit (Qiagen) y DNA purification kit (Promega). La concentración de DNA doble hebra será determinada mediante el kit ensayo BR y el uso de Qubit (Invitrogen). 
Las librerías de DNA serán preparadas de acuerdo al protocolo del fabricante utilizando para ello el Illumina Nextera XT DNA sample preparation kit (Illumina). Consistente en la fragmentación por "tagmentación, seguido de amplificación por PCR, la adición de los índices de secuenciación y la normalización basada en beads de las concentraciones de las librerías generadas antes de mezclarlas. Las librerías mezcladas serán secuenciadas en la plataforma de secuenciación MiSeq (Illumina) usando el kit de reactivos MiSeq v2 (Illumina) para 300 o 500 ciclos, para producir así dos reads de 150 o 250 pares de base. 
La calidad de la data cruda obtenida será medida mediante el software CutAdapt, eliminando todos los reads con menos de 40 pares de base de largo o un puntaje Q menor a 20. El ensamble de novo será llevado a cabo con el algoritmo Velvet, con un largo de k-mer de 35 hasta 95, para luego recuperar todos los contigs con al menos un largo de 200pb.
Luego se usará el pipeline de anotación RAST(15) y se asignarán funciones y se harán perfiles de abundancia de enzimas urulizando las herramientas de Integrated Microbial Genomes (IMG)(16). Se determinarán los genes involucrados en el metabolismo de carbohidratos y se agruparán de acuerdo a sus familias y su especificidad de sustrato y finalmente 
se deteminará si las enzimas participes de la fermentación ABE están codificadas por los grupos previamente determinados.

##  Resultados Esperados 
Tras la aplicación del protocolo de toma de muestras, cultivo y aislación espero obtener al menos 3 bacterias distintas fenotipicamente para enfrentarlas al desafío de butanol, de este espero obtener resultados similares a los obtenidos en la figura 1 

![Image of Figura 1](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/figura1.png)
Figura 1: Efectos de la adición de butanol a cultivos crecidos de Bacteria 1, Bacteria 2, Bacteria 3 cuantificado mediante conteo de Células viable (CFU)
El Butanol fue agregado a cultivos en la mitad de la fas exponencial en contraciónes %(peso/volumen) de 0(diamantes negros), 0,25 (cuadrados blancos), 0,5 (triangulos negros), 0,75(circulos blancos), 1,0 (circulos negros),1,25(triangulos negros), 1,5(cuadrados negros) y 2,0(diamantes blancos)
el ensayo fue llevado a cabo en triplicado y las barras de error representan la desviación estandar.

Tras el análisis de los genes involucrados en la fermentación ABE espero poder mostrar una tabla resumen de este tipo 
![Image of Figura 2](https://raw.githubusercontent.com/Daniel-Tichy/Bioinfo-Geno/master/figura2.jpg)
Tabla comparativa de la bacteria secuenciada con los genes presentes en el orden clostridia. 

## Referencias

1.-Lynd, L. & Laser, M. in Aqueous pretreatment of plant biomass for biological and chemical conversion to fuels and chemicals. (eds
Wyman, C. E.) 17-21. John Wiley & Sons, doi: 10.1002/9780470975831 (2013).

2.- Jones, D. T. & Woods, D. R. Acetone-butanol fermentation revisited. Microbiol. Rev. 50(4), 484 (1986).

3.- Bahl, H. & Dürre, P. Clostridia: biotechnology and medical applications. Wiley-VCH Verlag GmbH., doi: 10.1002/3527600108.fmatter_
indsub (2001).

4.-Atsumi, S. et al. Metabolic engineering of Escherichia coli for 1-butanol production. Metab. Eng. 10(6), 305-311, doi: 10.1016/j.
ymben.2007.08.003 (2008).

5.- Inui, M. et al. Expression of Clostridium acetobutylicum butanol synthetic genes in Escherichia coli. Appl. Microbiol. Biotechnol.
77(6), 1305-1316, doi: 10.1007/s00253-007-1257-5 (2008).

6.- Nielsen, D. R. et al. Engineering alternative butanol production platforms in heterologous bacteria. Metab. Eng. 11(4), 262-273, doi:
10.1016/j.ymben.2009.05.003 (2009).

7.-Yin, J., Chen, J.-C., Wu, Q. & Chen, G.-Q. Halophiles, coming stars for industrial biotechnology. Biotech. Adv. doi: 10.1016/j.
biotechadv.2014.10.008 (2014).

8.-Yue, H. et al. A seawater-based open and continuous process for polyhydroxyalkanoates production by recombinant Halomonas
campaniensis LS21 grown in mixed substrates. Biotechnol. Biofuels 7(1), 108, doi: 10.1186/1754-6834-7-108 (2014).

9.-Sarikhan, S. et al. Draft genome sequence of Nesterenkonia sp. strain F, isolated from Aran-Bidgol Salt Lake in Iran. J. Bacteriol.
193(19), 5580-5580, doi: 10.1128/JB.05808-11 (2011).

10.-Amiri, H. et al. Nesterenkonia sp. strain F, a halophilic bacterium producing acetone, butanol, and ethanol under aerobic conditions. Sci. 
Rep. 6, 18408; doi: 10.1038/srep18408 (2016).

11.-Azua-Bustos A, González-Silva C. Biotechnological Applications Derived from Microorganisms of the Atacama Desert. BioMed Research International. 
2014;2014:909312. doi:10.1155/2014/909312.(2014)

12.-Azua-Bustos A, Urrejola C, Vicuña R. Life at the dry edge: microorganisms of the Atacama Desert. The FEBS Letters. 2012;586(18):2939-2945

13.-Schneegurt MA. Media and Conditions for the Growth of Halophilic and Halotolerant Bacteria and Archaea in: Vreeland TH. Advances in understanding the biology of halophilic microorganisms. Dordrecht, Netherlands: ; Springer; 2016 

14.- Joensen KG, Tetzschner AMM, Iguchi A, Aarestrup FM, Scheutz F. Rapid and Easy In Silico Serotyping of Escherichia coli Isolates by Use of Whole-Genome Sequencing Data. Carroll KC, ed. Journal of Clinical Microbiology. 2015;53(8):2410-2426. doi:10.1128/JCM.00008-15.

15.-Aziz, R. K., et al. 2008. The RAST server: rapid annotations using subsystems technology. BMC Genomics 9:75

16.-Markowitz, V. M. et al. IMG ER: a system for microbial genome annotation expert review and curation. Bioinformatics 25(17),2271.2278, doi: 10.1093/bioinformatics/btp393 (2009).













