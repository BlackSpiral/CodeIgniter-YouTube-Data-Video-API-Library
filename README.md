CodeIgniter YouTube Data Video API Library
==========================================

Esta libreria ayuda a obtener la informacion de un video YouTube en especifico

NOTA:
_____
Se utiliza la API 2.0 de Youtube. --> https://developers.google.com/youtube/2.0/reference
Definición de los elementos XML (Media RSS, Esquema XML de YouTube, Esquema de Google Data) --> https://developers.google.com/youtube/2.0/reference#API_Request_XML_Element_Definitions


Modo de uso
___________
Copia el archivo en la carpeta de librerias de tu aplicacion - "./application/libraries/""

Invoca la clase

$this->load->library('youtube_video');
$this->youtube_video->youtube_data($youtube_url);

Donde $youtube_url puede ser de las siguientes formas:
	- http://www.youtube.com/watch?feature=player_embedded&v=sCvhhBySYzE  (con parametros)
	- http://www.youtube.com/watch?&v=sCvhhBySYzE
	- http://youtu.be/sCvhhBySYzE

Si la url es invalida o el ID no existe (incorrecto o eliminado)
retorna un valor null

Valores de retorno
__________________
$youtube_data['youtube_id']
$youtube_data['title']
$youtube_data['author']['name']
$youtube_data['author']['uri']
$youtube_data['category']
$youtube_data['published']
$youtube_data['updated']
$youtube_data['keywords'] (revisar funcione bien)
$youtube_data['statistics']['favoriteCount'] (indica el número de usuarios que han añadido un vídeo a su lista de favoritos.)
$youtube_data['statistics']['viewCount']
$youtube_data['duration'] (revisar videos d evarias horas)
$youtube_data['duration_format']
$youtube_data['description'] (regresa null si no hay)
$youtube_data['rating']['average'] (YouTube utiliza un sistema de puntuación de 1 a 5 en el que 1 es la puntuación más baja y 5 la mas alta.)
$youtube_data['rating']['numRaters'] (Cantidad de votantes)

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








si no hay descripcion retorna null $youtube_data['description']

Licencia
________
Copyright © 2013 - @PhiRequiem
GNU -> http://www.gnu.org/licenses/gpl.txt

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.