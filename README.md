# qr-bombero-asignaciones
Genera codigos qr para asignaciones de articulos 
<!DOCTYPE html>
<html>
<head>
    <title>Tu Página Web</title>
</head>
<body>
    <h1>GENERAR CODIGO QR PARA ASIGNAR</h1>
    <h2>Generar código QR</h2>
    <input type="text" id="datoInput" placeholder="Ingrese el dato">
    <button onclick="generarQR()">Generar QR</button>
    <div id="qrCode"></div>

    <script>
        function generarQR() {
            const dato = document.getElementById('datoInput').value;

            // Verificar si se ingresó un dato
            if (dato) {
                // Limpiar el contenedor del código QR
                document.getElementById('qrCode').innerHTML = '';

                // Generar el enlace al servicio web con el dato codificado
                const webURL = 'https://www.paginadecodigoqr.com/?dato=' + encodeURIComponent(dato);

                // Crear la etiqueta de imagen del código QR
                const qrImg = document.createElement('img');
                qrImg.src = 'https://api.qrserver.com/v1/create-qr-code/?data=' + encodeURIComponent(webURL);
                qrImg.alt = 'Código QR generado';
