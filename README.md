# aula_jquery_ajax
Introdução ao JQuery e Ajax

Index.html

<!DOCTYPE html>
<html lang="pt-br">
<head>
	<meta charset="utf-8" />
	<title>Minha Página</title>
	<script type="text/javascript" src="js/JS jquery-3.6.0.min.js"></script>
	<script type="text/javascript" src="js/JS main.js"></script>
</head>
<body>
	<input id="cep">
	<button type="button" onclick="consultaCep()">Consultar</button>
	<p id="logradouro"></p>
	<p id="bairro"></p>
	<p id="localidade"></p>
	<p id="uf"></p>
</body>
</html>

JS main.js

function consultaCep(){
	var cep = document.getElementById("cep").value;
	var url = "https://viacep.com.br/ws/" + cep + "/json/";
	console.log(url);
	$.ajax(
	{
		url: "https://viacep.com.br/ws/14800390/json/",
		type: "GET",
		success: function(response){
			console.log(response);
			$("#logradouro").html(response.logradouro);
			//document.getElementById("logradouro").innerHTML = response.logradouro;
			document.getElementById("bairro").innerHTML = response.bairro;
			document.getElementById("localidade").innerHTML = response.localidade;
			document.getElementById("uf").innerHTML = response.uf;
			//alert(response.logradouro);
		}
	})
}
