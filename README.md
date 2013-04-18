# CodeIgniter YouTube Data Video API Library

<p>Esta libreria ayuda a obtener la información de un video YouTube en específico</p>

<strong>NOTA:</strong>
> Se utiliza la API 2.0 de Youtube. --> > https://developers.google.com/youtube/2.0/reference
>
> Definición de los elementos XML (Media RSS, Esquema XML de YouTube, Esquema de Google Data) --> https://developers.google.com/youtube/2.0/reference#API_Request_XML_Element_Definitions</p>


<h2>Modo de uso</h2>

> Copia el archivo en la carpeta de librerias de tu aplicacion - "./application/libraries/""

<strong>Invocar la clase</strong>

<pre>
	$this->load->library('youtube_video');
	$this->youtube_video->youtube_data($youtube_url);
</pre>

<small>Donde $youtube_url puede ser de las siguientes formas:
	<ul>
		<li>http://www.youtube.com/watch?feature=player_embedded&v=sCvhhBySYzE  (con parametros)</li>
		<li>http://www.youtube.com/watch?&v=sCvhhBySYzE</li>
		<li>http://youtu.be/sCvhhBySYzE</li>
	</ul>
</small>

>Si la url es inválida o el ID no existe (incorrecto o eliminado) retorna un valor null

<strong>Valores de retorno</strong>
<pre>
$youtube_data['youtube_id'] 		//Id del video
$youtube_data['title'] 	//titulo del video
$youtube_data['author']['name'] 		//nombre del autor
$youtube_data['author']['uri'] 		//(Url Autor (perfi))
$youtube_data['category'] 		//categoría asignada
$youtube_data['published'] 		//(fecha de publicación)
$youtube_data['updated'] 		//(fecha actualizado)
$youtube_data['keywords'] 		//(revisar funcione bien)
$youtube_data['statistics']['favoriteCount'] 		//(indica el número de usuarios que han añadido un vídeo a su lista de favoritos.) (si no existe regresa null)
$youtube_data['statistics']['viewCount'] 		//Numero de veces visto (si no existe regresa null)
$youtube_data['duration'] 		//(duración en segundos)
$youtube_data['duration_format'] 		//(duración en h:m:s)
$youtube_data['description'] 		//(regresa null si no hay)
$youtube_data['rating']['average'] 		//(YouTube utiliza un sistema de puntuación de 1 a 5 en el que 1 es la puntuación más baja y 5 la mas alta.)
$youtube_data['rating']['numRaters'] 		//(Cantidad de votantes)

--- imagenes url ---
$youtube_data['0_thumbnail']['url']
$youtube_data['1_thumbnail']['url']
$youtube_data['2_thumbnail']['url']
$youtube_data['3_thumbnail']['url']

--- imagenes height ---
$youtube_data['0_thumbnail']['height']
$youtube_data['1_thumbnail']['height']
$youtube_data['2_thumbnail']['height']
$youtube_data['3_thumbnail']['height']

--- imagenes width ---
$youtube_data['0_thumbnail']['width']
$youtube_data['1_thumbnail']['width']
$youtube_data['2_thumbnail']['width']
$youtube_data['3_thumbnail']['width']

--- imagenes tiempo de captura ---
$youtube_data['0_thumbnail']['time']
$youtube_data['1_thumbnail']['time']
$youtube_data['2_thumbnail']['time']
$youtube_data['3_thumbnail']['time']
</pre>

<strong>Ejemplo de uso</strong>
<pre>
<?php
$youtube_url = 'http://www.youtube.com/watch?v=U6Vf4zZiKAA';
$this->load->library('youtube_video');
if($youtube_data = $this->youtube_video->youtube_data($youtube_url)) {
	echo '<strong>ID: </strong>'.$youtube_data['youtube_id'].'<br>';
	echo '<strong>Titulo: </strong>'.$youtube_data['title'].'<br>';
	echo '<strong>Autor: </strong>'.$youtube_data['author']['name'].'<br>';
	echo '<strong>Url Autor (perfi): </strong>'.$youtube_data['author']['uri'].'<br>';
} else {
	echo 'Upss!! El video no existe - Revisa tu URL ¯\(°_o)/¯';
}
?>
</pre>

<strong>NOTA Para obtener solo el ID del video sin llamar a la API:</strong>
<pre>
	$youtube_url = 'http://www.youtube.com/watch?v=U6Vf4zZiKAA';
	$this->load->library('youtube_video');
	echo $this->youtube_video->youtube_id($youtube_url);
</pre>

### Licencia
<p>
Copyright © 2013 - @PhiRequiem <br>
GNU -> http://www.gnu.org/licenses/gpl.txt <br><br>

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.<br><br>

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.<br><br>

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>. </p>