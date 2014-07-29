crud
====

crud 

index 

<?php 
require 'Conectar.php';
require 'verificar.php';

$mensaje = NULL;
if (isset($_POST["guardar"])) {
    $conectar = new verificar;
    $conectar->codigo = $_POST["codigo"];
    $conectar->nombre = $_POST["nombre"];
    $conectar->tecnologia = $_POST["tecnologia"];
    $conectar->capacidad = $_POST["capacidad"];
    $conectar->verificar();
    $mensaje = $conectar->mensaje;
}
?>

<!DOCTYPE html>
<html>

<head>
	<meta charset='utf-8'>﻿	
	<link href="Stylo.css" rel="stylesheet" type="text/css">

    <center><nav >
        <ul class='nav'>
            <li><a href="Index.html"> Inicio </a></li>
            <li><a href="#"> Registros </a>
                <ul>
                <li><a href="Profesores.html"> Profesores </a></li>
                <li><a href="Materias.html"> Asignaturas </a></li>
                <li><a href="Laboratorios.html"> Laboratorios </a></li>
                </ul>
            </li>
            <li><a href="Consultas.html"> Consultas </a></li>
            <li><a href="Asignacion.html"> Asignación</a></li>
        </ul>
    </nav></center>	

</head>
	

<body>

	<div class='Titulo'>
		<br><center><h2>Registros de Laboratorios</h2></center>
	</div>

	<div id='Contenedor'>
                <strong> <?php echo $mensaje;?></strong>
		<div id='Laboratorios' class='Formu'>
			<h3 class='Titulo'>Información Laboratorios</h3>
                        
			<form action='<?php echo $_SERVER["PHP_SELF"];?>' method='POST' name='CrudLaboratorios'>
				<center><table border='0px'>
				<tr><center><td>Codigo: </td></center>
				<td><center><input type='text' id='CodgoLab' name='codigo'></center></td></tr>
				<tr><center><td>Nombre: </td></center>
				<td><center><input type='text' id='NombreLab' name='nombre'></center></td></tr>
				<tr><center><td>Técnologia: </td></center>
				<td><center><input type='text' id='TecnologiaLab' name='tecnologia'></center></td></tr>
				<tr><center><td>Capacidad: </td></center>
				<td><center><input type='text' id='CapacidadLab' name='capacidad'></center></td></tr>
				</table></center><br>
		</div>	

		<div id='Botones' class='Botones'>
				<input type='button' name='boton' id='boton' value='Buscar'><br>
                                <input type='submit' name='guardar' id='boton' value='Guardar'><br>
				<input type='button' name='boton' id='boton' value='Modificar'/><br>
				<input type='button' name='boton' id='boton' value='Actualizar'/><br>
				<input type='button' name='boton' id='boton' value='Eliminar'><br>
			</form>
		</div>		

	</div>

</body>

</html>
