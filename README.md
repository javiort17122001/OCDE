# Analisis global de crecimiento verde, calidad de vida y emisiones de carbono de la OCDE

Objetivo: Analizar la relacion entre la emision de dioxido de carbono, el crecimiento verde y la calidad de vida de los paises de la OCDE en el periodo 2008-2024<br/><br/>
Hipotesis: Aquellos paises que emiten mayor emision de dioxido de carbono tendran menor crecimiento verde y calidad de vida a diferencia de aquellas economias que emiten menos CO<sub>2</sub>
# Descripcion general
1. Obtuvo las diversas variables economicas, sociales y ambientales pertenecientes al indice de una vida mejor de la OCDE, indice de crecimiento verde e inclusivo y emision de CO<sub>2</sub> de la base de datos del Banco Mundial y de la OCDE obteniendo el archivo "Datos"
2. Limpieza de la base de datos con el uso de pandas y otras bibliotecas de python para obtener el archivos "final"
3. Procede a realizar el analisis de la base de datos "final" con el uso de python con la aplicacion de analisis estadistico (analisis de Componentes Principales) y los algoritmos de clasificacion K-means y DBSCAN

# Resultados
- Al aplicar el PCA principalmente se obtiene las siguientes componentes principales:
<table>
  <tr>
    <th>Componentes</th>
    <th>PC1</th>
  <tr>
  <tr>
    <td>Tasa_Mortalidad</td>
    <td>0.247245</td>
  <tr>
    <tr>
    <td>Indice_Crecimiento_Verde</td>
    <td>0.243851</td>
  <tr>
    <tr>
    <td>Ajuste_Neto_Nacional</td>
    <td>0.242661</td>
  <tr>
    <tr>
    <td>Tasa_Homicidios</td>
    <td>0.242593</td>
  <tr>
    <tr>
    <td>Indice_Gini/td>
    <td>0.0.237303</td>
  <tr>
    <tr>
    <td>Personal_earning</td>
    <td>0.236396</td>
  <tr>
    <tr>
    <td>Habilidades_Estudiantes</td>
    <td>0.234638</td>
  <tr>
    <tr>
    <td>Escolaridad</td>
    <td>0.227296</td>
  <tr>
</table>

<table>
  <tr>
    <th>Componentes</th>
    <th>PC2</th>
  <tr>
  <tr>
    <td>Empleo</td>
    <td>0.382799</td>
  <tr>
    <tr>
    <td>Polucion_Aire</td>
    <td>0.320175</td>
  <tr>
    <tr>
    <td>Renta_Recursos_Naturales</td>
    <td>0.265447</td>
  <tr>
    <tr>
    <td>Consumo_Energia_Renovable</td>
    <td>0.255079</td>
  <tr>
    <tr>
    <td>Intensidad_Energetica/td>
    <td>0.221140</td>
  <tr>
    <tr>
    <td>Desempleo_Largo_Plazo</td>
    <td>0.217195</td>
  <tr>
    <tr>
    <td>Agua_Dulce_Renovable</td>
    <td>0.372427</td>
  <tr>
    <tr>
    <td>Ratio_Dependencia</td>
    <td>0.204147</td>
  <tr>
</table><br/>
El PC1 tiene cargas altas en tasa de mortalidad, tasa de homicidios, índice de crecimiento verde y índice de Gini, por lo que combina el PC1 variables de salud, de seguridad, de economía y de capital humano, por lo que parece ser este componente un índice de desarrollo y bienestar socioeconómico, un país con puntuación alta podría indicar mayores desafíos en el desarrollo y el bienestar social y un país con puntuación baja mayor salud y bienestar. <br/><br/>
Por el lado del PC2 tiene cargas altas en empleo, desempleo, la polución del aire, así como el consumo de energías renovables y del agua dulce renovable son las variables con mayor carga, por lo que este componente es una medida del mercado laboral con sostenibilidad ambiental, este indicador nos permite observar aquellas economías con mercados laborales robustos con alta huella ambiental y aquellos países con mayores problemas laborales y más enfocados en la sostenibilidad.<br/><br/><br/><br/>


* Para optimizar el uso de K-means y DBSCAN, el numero optimo de clusteres es 2, a partir del metodo del codo y el indice de la silueta, principalmente por la gran diferencia de silueta al variar el numero de clusteres 
 <img width="921" height="434" alt="image" src="https://github.com/user-attachments/assets/6a740cc1-f260-42b0-bdb3-d8e76e0624c6" />
<img width="923" height="456" alt="image" src="https://github.com/user-attachments/assets/7647cf47-6768-4779-9c76-bcaabc427b20" />
<br/><br/><br/><br/>

# K-MEANS

+ Asi pues al aplicar el algoritmo K-means que se fundamenta en distanicia euclidiana, se obtiene este plano con los valores de las cargas de los componentes principales de cada pais, asi como los 2 grupos creados
<img width="1355" height="657" alt="image" src="https://github.com/user-attachments/assets/8f560708-2639-4bac-b5d5-544434ed618f" />

<table>
  <tr>
    <th>Clúster</th>
    <th>Países</th>
  <tr>
  <tr>
    <td>0</td>
    <td>Alemania, Australia, Austria, Bélgica, Canadá, Corea Sur, Dinamarca, Eslovenia, España, Estados Unidos, Estonia, Finlandia, Francia, Grecia, Hungría, Irlanda, Islandia, Israel, Italia, Japón, Letonia, Lituania, Luxemburgo, Noruega, Nueva Zelandia, Países Bajos, Polonia, Portugal, Reino Unido, Republica Checa, República Eslovaca, Suecia, Suiza </td>
  <tr>
    <tr>
    <td>1</td>
    <td>Brasil, Chile, Colombia, Costa Rica, México, Rusia, Turquía</td>
</table><br/>


+	El clúster 0 tiene países con mayor renta de recursos naturales y tienen mayor consumo de energías renovables.
+ El clúster 1 muestra menor desempleo a largo plazo, aunque en el clúster 0 las ganancias de la población se mucho mayor que los del clúster 1, y por lo tanto también el ahorro es mayor.
+ El clúster 0 muestra mayores niveles de emisiones de dióxido de carbono, así como mayor contaminación que el clúster 1, lo que provoca también que el clúster 0 muestre mayor eficiencia.
*	El clúster 1 muestra mayores desafíos sociales como una mayor desigualdad y mucho mayores tasas de mortalidad y de homicidios, así como mayor concentración de mercado.
*	El clúster 0 tiene países con mayor renta de recursos naturales y tienen mayor consumo de energías renovables.

Donde dichos clusteres, ya sea en cualquier año no se modifica implicando que hay una diferencia esencial entre estas dos agrupaciones.<br/>
Mas allá de la evolución de los clústeres, es relevante analizar la inercia temporal del componente principal 1, es decir, la persistencia de las posiciones de los países en periodo de estudio (2008-2024). Para cuantificar esta inercia, se calculó la correlación de Pearson, así como la correlación de Spearman entre el periodo inicial y el final, al realizar este cálculo es obtuvieron los siguientes resultados:<br/><br/>
<p align="center"> Pearson: r = 0.9653 <br/><br/> </p>
<p align="center"> Spearman: ρ = 0.9482<br/><br/> </p>
Estos cálculos son mayores a 0.9 esto implica que hay una inercia muy alta y se mantengan los países consistentemente en esa posición. Esto implica que los factores subyacentes del desarrollo como las instituciones, el capital humano y desigualdad estructural cambian lentamente y son altamente persistentes que requiere transformaciones profundas, las cuales requieren décadas. <br/>


Los hallazgos  revelan que se puede dividir la OCDE en 2 agrupaciones de países, los cuales son los países desarrollados conformados por muchos países de Europa  y de Estados Unidos y por el otro lado los países emergentes conformados por los países latinoamericanos junto con Rusia y Turquía, donde los países desarrollados en general son países más dedicados al crecimiento del mercado laboral del carácter social y con desarrollo en el bienestar, mientras los países emergentes están más caracterizados con mercados laborales más sostenibles con desafíos sociales principalmente.

# DBSCAN
A diferencia del K-means para el DBSCAN se necesita una estimación de la mejor épsilon posible (eps), así como del mínimo de punto (min_samples) pues el algoritmo DBSCAN depende críticamente de estos dos parámetros, todo mediante el método del codo y la distribución de la densidad en los datos.

Para seleccionar las variables eps óptima y  min_samples se realiza un proceso de iteración sobre una lista de candidatos para min_samples y se estima un eps usando el método del codo para cada candidato a min_samples, luego se va refinando la eps en un radio muy cercano para que al final se evalúa cada combinación de (eps ,min_samples) basándose principal en el índice de silueta y se selecciona finalmente la combinación con mejores resultados.

<img width="928" height="413" alt="image" src="https://github.com/user-attachments/assets/9d032f58-3560-42ba-94a5-9fba0b28fbfa" />

<img width="1354" height="642" alt="image" src="https://github.com/user-attachments/assets/3c23fb49-d96f-45ef-8265-696334f6f703" />


1.	En el clúster 1 muestran a 3 países latinoamericanos exactamente: México, Brasil y Colombia. Aunque no poder económico no está mal, muchas características sociales y económicas se encuentran muy por debajo de los demás países.
2.	Otros países que dependencia de los recursos no renovables y esto también conlleva de la peor calidad del aire como Rusia y Polonia.
3.	Corea del Sur es de los países que más han crecido en los últimos años, con grandes resultados en educación y salud aun con un pobre gasto público y la peor calidad ambiental.

Este modelo identifica los valores atípicos, así como los casos de heterogeneidad estructural que merecen análisis económico individualizado, como el bajo ingreso en instituciones de Latinoamérica aun con buen ingreso o la dependencia de recursos no renovables de Rusia, Polonia y Corea de Sur a pesar de su crecimiento económico y tecnológico.








