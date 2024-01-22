<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Formulario de Solicitud de Empleo</title>
</head>
<body>

<?php
// Verifica si el formulario ha sido enviado
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Recopila los datos del formulario
    $nombre = $_POST["nombre"];
    $direccion = $_POST["direccion"];
    $telefono = $_POST["telefono"];
    $experiencia = $_POST["experiencia"];
    $motivacion = $_POST["motivacion"];

    // Puedes realizar validaciones adicionales aquí

    // Muestra los datos enviados
    echo "<h2>Información recibida:</h2>";
    echo "<p><strong>Nombre:</strong> $nombre</p>";
    echo "<p><strong>Dirección:</strong> $direccion</p>";
    echo "<p><strong>Teléfono:</strong> $telefono</p>";
    echo "<p><strong>Experiencia Laboral:</strong> $experiencia</p>";
    echo "<p><strong>Motivación:</strong> $motivacion</p>";

    // Puedes procesar los datos recibidos, como almacenarlos en una base de datos, enviar por correo electrónico, etc.
    // Aquí se muestra un ejemplo de cómo enviar un correo electrónico (requiere configuración adicional en tu servidor)
    $destinatario = "tu@email.com";
    $asunto = "Solicitud de Empleo - $nombre";
    $mensaje = "Nombre: $nombre\nDirección: $direccion\nTeléfono: $telefono\nExperiencia Laboral: $experiencia\nMotivación: $motivacion";

    // Descomenta la línea siguiente para enviar el correo (asegúrate de configurar correctamente el servidor de correo)
    // mail($destinatario, $asunto, $mensaje);
}
?>

<h1>Formulario de Solicitud de Empleo</h1>

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>">
    <label for="nombre">Nombre:</label>
    <input type="text" name="nombre" required><br>

    <label for="direccion">Dirección:</label>
    <input type="text" name="direccion" required><br>

    <label for="telefono">Teléfono:</label>
    <input type="tel" name="telefono" required><br>

    <label for="experiencia">Experiencia Laboral:</label>
    <textarea name="experiencia" rows="4" required></textarea><br>

    <label for="motivacion">Motivación para el Empleo:</label>
    <textarea name="motivacion" rows="4" required></textarea><br>

    <input type="submit" value="Enviar Solicitud">
</form>

</body>
</html>
