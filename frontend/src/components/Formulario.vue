<template>
    <div>
        <?php   
//ESPECIFICA EL CONTENIDO
$meta=array(
	'tituloPagina'=>'why use appdvice - Appdvice. Automatize your decisions',
	'metaIMG'=>'partes-del-cerebro.png',
	'metaDescripcion'=>'Lorem Ipsum',
	'metaKeywords'=>'brain parts, decission algorithms',
	//Booleanos para ROBOTS.TXT index=0 (no index) follow=0 (no follow)
	'index'=>1,
	'follow'=>1
);
//CARGA EL HEAD
require_once'mod/head.php';
?>
<?php //BODY AQUÍ ABAJO 
require_once'mod/header.php';
$preguntasFormulario= array('0',
	'¿Requiere del gasto de muchos recursos (tiempo, dinero...) ?',
	'¿Cómo de difíciles son las acciones que conlleva tomar esta decisión?',
	'¿Conlleva algún riesgo? ¿Cómo de bien conoces las consecuencias de esta decisión?',
	'¿Cuánto disfrutarías haciéndolo?',
	'¿Tendría un impacto positivo en tu vida?',
	'¿Cuánto te acerca a tus sueños esta decisión?',
	'¿Afectará a la gente que te importa?'		);
?>
	<form method="get" action="algoritmo.php">
<?php
for ($i=1; $i <8 ; $i++) { 
	echo '
		<div class="">
		<label>'.$preguntasFormulario[$i].'</label>
		<input id="pregunta'.$i.'" type="range" name="pregunta'.$i.'" min="0" max="100">
		</div>
	';
}
?>
		<input type="submit" name="enviar">
	</form>
    </div>
</template>