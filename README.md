- 👋 Hi, I’m @Ksjswk9
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Ksjswk9/Ksjswk9 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// == Guión de usuario ==
// @name Netflix - Cookie de importación
// @versión 1.1
// @description Importar cookies de Netflix
// @match http*://*.netflix.com/*
// @copyright 2013+, Tú
// @espacio de nombres https://greasyfork.org/users/32340
// ==/UserScript==

función setCookie(clave, valor) {
	var hoje = nueva Fecha();
	minuto = 999 * 24 * 60;
	var expira = new Date(hoje.getTime() + minuto * 60 * 1000);
	var expira = expira.toGMTString();
    var dominio2 = ';dominio=.netflix.com';
	documento.cookie = clave + '=' + valor + ';caduca=' + caduca + dominio2;
}

var msg = "Coloque la galleta Aqui!!!";

función aplicar(){
	cont = $('#cookie_text').val();
	if (longitud continua > 0){
		txt = cont.split('\n');
		lentxt = txt.longitud;

		para (i = 0; i < lentxt; i++){
			línea = txt[i].split('\t');
			len = linea.longitud;
			clave = linea[len-2];
			valor = linea[len-1];
			setCookie(clave, valor);
		}

		alert('Se carga la cookie... Actualizando');
		ubicación.href='https://movies.netflix.com/WiHome';
	} otra alerta (mensaje);
}

local = $('.formulario-contenedor');
if ($(local)[0] == null) local = $('header:first').next();
if (ubicación.href.indexOf('películas') == -1)
    $(local).children().first().before('<div style="width: 100%; max-width: 500px; padding: 5px;font-weight: bold; border: #000 solid 4px; background -color: #FFF;text-align: center;"><span>'+msg+'</span><br><textarea id="cookie_text" style="width:98%; height: 400px;">< /textarea><br><center><a href="#" onclick="return false;" style="color:#FFF; background-color: red;" id="cookie_login">Cookie de inicio de sesión</a> </center></div>');
$('#cookie_login').bind('clic', aplicar);

vacío (0);
