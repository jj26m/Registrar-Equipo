<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Registro Equipos F1 - Aurex Corporation</title>
    <style>
        body {
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #header {
            background-color: red;
            padding: 10px;
            font-size: 2em;
            color: black;
        }
        .form-container {
            margin-top: 20px;
        }
        .input-box {
            margin: 10px;
            padding: 10px;
            font-size: 1.2em;
            width: 250px;
        }
        .submit-btn {
            padding: 10px;
            font-size: 1.2em;
            background-color: blue;
            color: white;
            border: none;
            cursor: pointer;
        }
        .submit-btn:hover {
            background-color: darkblue;
        }
    </style>
</head>
<body>

    <div id="header">Aurex Corporation - Registro Equipos F1</div>
    <div class="form-container">
        <h2>Formulario para Registro de Equipo F1</h2>
        <form id="formularioEquipo">
            <input type="text" id="nombreEquipo" class="input-box" placeholder="Nombre del Equipo" required><br>
            <input type="text" id="dueno" class="input-box" placeholder="Dueño (@)" required><br>
            <input type="text" id="miembros" class="input-box" placeholder="Miembros" required><br>
            <input type="text" id="color" class="input-box" placeholder="Color" required><br>
            <input type="file" id="logo" class="input-box" required><br>
            <button type="submit" class="submit-btn">Registrar Equipo</button>
        </form>
    </div>

    <script>
        document.getElementById('formularioEquipo').addEventListener('submit', function(event) {
            event.preventDefault();

            let formData = new FormData();
            formData.append("nombreEquipo", document.getElementById('nombreEquipo').value);
            formData.append("dueno", document.getElementById('dueno').value);
            formData.append("miembros", document.getElementById('miembros').value);
            formData.append("color", document.getElementById('color').value);
            formData.append("logo", document.getElementById('logo').files[0]);

            fetch('https://discord.com/api/webhooks/1311859474004312064/FsFuWn6JBkIbK8bDkdr0ZQugA6LoRqvr0FYJQqa3x7V-I8YGz2QMhn-hrCSNxo19iS3G', {
                method: 'POST',
                body: formData
            })
            .then(response => response.json())
            .then(data => {
                alert('Equipo registrado con éxito');
            })
            .catch(error => {
                alert('Error al registrar el equipo');
            });
        });
    </script>

    <div>Desarrollado por: jj26m</div>

</body>
</html>
