<h1>Cálculo para equalização do histograma de uma imagem em tons de cinza</h1>

<h5>Diversos sites da Internet trazém fórmulas para realizar a equalização de um histograma. Porém para para egressos dos cursos de tecnologia e afins como Análise Desenvolvimento de Sistemas, Sistemas para Internet tem pouca afinidade com cálculos.</h5>
<h6>Histograma</h6>

<p>1-)Este histograma tem repreentado uma imagem de 3bits ou seja 8 tons de cinza. Na tabela cada tom de cinza tem uma quantidade de pixel, a partir disso é calculado a massa de probabilidade, que consiste em pegar a quantidade de elementos de uma classe e dividir pela quantidade tortal de elementos do conjunto. Essa é a primeira parte da equalização do histograma </p>

<table>
	<tr>
		<th>tons de cinza</th>
		<th>quantidade de pixels </th>
		<th>massa de probabilidade</th>
	</tr>
	<tr>
		<td>0</td>
		<td>790</td>
		<td>0.19</td>
	</tr>
	<tr>
		<td>1</td>
		<td>1023</td>
		<td>0.25</td>
	</tr>
	<tr>
		<td>2</td>
		<td>850</td>
		<td>0.21</td>
	</tr>
	<tr>
		<td>3</td>
		<td>656</td>
		<td>0.16</td>
	</tr>
	<tr>
		<td>4</td>
		<td>329</td>
		<td>0.08</td>
	</tr>
	<tr>
		<td>5</td>
		<td>245</td>
		<td>0.06</td>
	</tr>
	<tr>
		<td>6</td>
		<td>122</td>
		<td>0.03</td>
	</tr>
	<tr>
		<td>7</td>
		<td>81</td>
		<td>0.02</td>
	</tr>

	
	
</table>


<p>2-) A segunda parte é o cálculo usando a função de distribuição acumulada( cdf ) que nada mais é doque ir somando o valor dos bits anteriores da imagem ou seja a posição 1 soma com a posição 0 e assim por diante acumulando os valores</p>

<table>
	<tr>
		<th>tons de cinza</th>
		<th>quantidade de pixels </th>
		<th>massa de probabilidade</th>
		<th>cdf</th>
	</tr>
	<tr>
		<td>0</td>
		<td>790</td>
		<td>0.19</td>
		<td>0.19</td>
	</tr>
	<tr>
		<td>1</td>
		<td>1023</td>
		<td>0.25</td>
		<td>0.44</td>
	</tr>
	<tr>
		<td>2</td>
		<td>850</td>
		<td>0.21</td>
		<td>0.65</td>
	</tr>
	<tr>
		<td>3</td>
		<td>656</td>
		<td>0.16</td>
		<td>0.81</td>
	</tr>
	<tr>
		<td>4</td>
		<td>329</td>
		<td>0.08</td>
		<td>0.89</td>
	</tr>
	<tr>
		<td>5</td>
		<td>245</td>
		<td>0.06</td>
		<td>0.95</td>
	</tr>
	<tr>
		<td>6</td>
		<td>122</td>
		<td>0.03</td>
		<td>0.98</td>
	</tr>
	<tr>
		<td>7</td>
		<td>81</td>
		<td>0.02</td>
		<td>1</td>
	</tr>

	
	
</table>

<p>3-) Na parte final os valores da equação cdf devem ser multiplicados por 7 para fazer a normalização, e definir a localização final no histograma</p>

<table>
	<tr>
		<th>tons de cinza</th>
		<th>quantidade de pixels </th>
		<th>massa de probabilidade</th>
		<th>cdf</th>
		<th>normalização( multiplica por 7 )</th>
		<th>bit final</th>
		<th>valor da massa</th>
	</tr>
	<tr>
		<td>0</td>
		<td>790</td>
		<td>0.19</td>
		<td>0.19</td>
	</tr>
	<tr>
		<td>1</td>
		<td>1023</td>
		<td>0.25</td>
		<td>0.44</td>
	</tr>
	<tr>
		<td>2</td>
		<td>850</td>
		<td>0.21</td>
		<td>0.65</td>
	</tr>
	<tr>
		<td>3</td>
		<td>656</td>
		<td>0.16</td>
		<td>0.81</td>
	</tr>
	<tr>
		<td>4</td>
		<td>329</td>
		<td>0.08</td>
		<td>0.89</td>
	</tr>
	<tr>
		<td>5</td>
		<td>245</td>
		<td>0.06</td>
		<td>0.95</td>
	</tr>
	<tr>
		<td>6</td>
		<td>122</td>
		<td>0.03</td>
		<td>0.98</td>
	</tr>
	<tr>
		<td>7</td>
		<td>81</td>
		<td>0.02</td>
		<td>1</td>
	</tr>

	
	
</table>
