<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Registro Pilotos F1 - Aurex Corporation</title>
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

    <div id="header">Aurex Corporation - Registro Pilotos F1</div>
    <div class="form-container">
        <h2>Formulario para Registro de Piloto F1</h2>
        <form id="formularioPiloto">
            <input type="text" id="nombreIC" class="input-box" placeholder="Nombre IC" required><br>
            <input type="number" id="edadIC" class="input-box" placeholder="Edad IC" required><br>
            <input type="text" id="user" class="input-box" placeholder="User" required><br>
            <input type="number" id="numeroPiloto" class="input-box" placeholder="Número de Piloto" required><br>
            <input type="file" id="fotoPiloto" class="input-box" required><br>
            <button type="submit" class="submit-btn">Registrar Piloto</button>
        </form>
    </div>

    <script>
        document.getElementById('formularioPiloto').addEventListener('submit', function(event) {
            event.preventDefault();

            let formData = new FormData();
            formData.append("nombreIC", document.getElementById('nombreIC').value);
            formData.append("edadIC", document.getElementById('edadIC').value);
            formData.append("user", document.getElementById('user').value);
            formData.append("numeroPiloto", document.getElementById('numeroPiloto').value);
            formData.append("fotoPiloto", document.getElementById('fotoPiloto').files[0]);

            fetch('https://discord.com/api/webhooks/1311858886243778560/bNo814xfHYVQR6v-yJLpagg1gZovujZXMPFGVOPhQ8O4QmslJNskOKJDTchfOPpp8XET', {
                method: 'POST',
                body: formData
            })
            .then(response => response.json())
            .then(data => alert('Piloto registrado con éxito'))
            .catch(error => alert('Error al registrar el piloto'));
        });
    </script>

    <div>Desarrollado por: jj26m</div>

</body>
</html>
