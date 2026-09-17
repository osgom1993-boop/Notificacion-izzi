# Notificacion-izzi
Envia nota al cliente
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notificación Izzi</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f2f2f2; padding: 20px; }
        .card { background: white; padding: 20px; border-radius: 10px; max-width: 350px; margin: auto; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        h2 { color: #00529B; text-align: center; }
        label { font-weight: bold; font-size: 14px; display: block; margin-top: 10px; }
        input { width: 100%; padding: 10px; margin-top: 5px; border: 1px solid #ccc; border-radius: 5px; box-sizing: border-box; }
        button { width: 100%; background-color: #25D366; color: white; border: none; padding: 12px; font-size: 16px; font-weight: bold; border-radius: 5px; margin-top: 20px; cursor: pointer; }
    </style>
</head>
<body>

<div class="card">
    <h2>Aviso de Visita Izzi</h2>
    
    <label for="tel">Teléfono (10 dígitos):</label>
    <input type="tel" id="tel" placeholder="Ej. 5512345678">

    <label for="nombre">Nombre del cliente:</label>
    <input type="text" id="nombre" placeholder="Ej. Juan Pérez">

    <label for="cuenta">Número de cuenta:</label>
    <input type="text" id="cuenta" placeholder="Ej. 1234567">

    <label for="orden">Número de orden:</label>
    <input type="text" id="orden" placeholder="Ej. 9876543">

    <button onclick="enviarWhatsApp()">ABRIR EN WHATSAPP</button>
</div>

<script>
function enviarWhatsApp() {
    let tel = document.getElementById('tel').value.trim().replace(/\D/g, '');
    let nombre = document.getElementById('nombre').value.trim();
    let cuenta = document.getElementById('cuenta').value.trim();
    let orden = document.getElementById('orden').value.trim();

    if (!tel) {
        alert("Por favor ingresa un número de teléfono.");
        return;
    }

    if (tel.length === 10) {
        tel = "52" + tel;
    }

    let mensaje = `Hola buenos días me comunico de Izzi para atender su falla a nombre de ${nombre}, número de cuenta ${cuenta} y número de orden ${orden}.\n\n¿Podrá atender en este momento?`;

    let url = `https://wa.me/${tel}?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
}
</script>

</body>
</html>
