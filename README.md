<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Datos de Cuenta Corriente</title>
  <style>
    * { box-sizing: border-box; }
    body {
      font-family: Arial, Helvetica, sans-serif;
      background: #f2f4f8;
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
    }
    .card {
      background: #fff;
      max-width: 420px;
      width: 100%;
      padding: 28px;
      border-radius: 12px;
      box-shadow: 0 4px 14px rgba(0,0,0,.12);
    }
    h1 { font-size: 1.3rem; text-align: center; color: #1a3c7a; margin-top: 0; }
    .row { padding: 10px 0; border-bottom: 1px solid #e5e8ee; }
    .label { font-size: .75rem; color: #6b7280; text-transform: uppercase; }
    .value { font-size: 1.05rem; font-weight: bold; word-break: break-all; }
    button {
      margin-top: 6px; padding: 4px 10px; font-size: .8rem;
      border: 1px solid #1a3c7a; background: #fff; color: #1a3c7a;
      border-radius: 6px; cursor: pointer;
    }
    button:hover { background: #1a3c7a; color: #fff; }
    #qrcode { display: flex; justify-content: center; margin-top: 24px; }
    .nota { text-align: center; font-size: .75rem; color: #6b7280; margin-top: 10px; }
  </style>
</head>
<body>
  <div class="card">
    <h1>Datos para Transferencia</h1>

    <div class="row">
      <div class="label">Titular</div>
      <div class="value" id="titular">CLAUDIA ROBIN GONZALEZ</div>
    </div>
    <div class="row">
      <div class="label">Banco / Tipo de cuenta</div>
      <div class="value">Banco de Chile – Cuenta Corriente</div>
    </div>
    <div class="row">
      <div class="label">N.º de cuenta</div>
      <div class="value" id="cuenta">2500076703</div>
      <button onclick="copiar('cuenta')">Copiar</button>
    </div>
    <div class="row">
      <div class="label">RUT</div>
      <div class="value" id="rut">12592827-7</div>
      <button onclick="copiar('rut')">Copiar</button>
    </div>
    <div class="row">
      <div class="label">Correo electrónico</div>
      <div class="value" id="correo">bingo2026oxford@gmail.com</div>
      <button onclick="copiar('correo')">Copiar</button>
    </div>

    <div id="qrcode"></div>
    <p class="nota">Escanee el código QR para abrir esta página.</p>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
  <script>
    new QRCode(document.getElementById("qrcode"), {
      text: window.location.href,
      width: 180,
      height: 180
    });

    function copiar(id) {
      const texto = document.getElementById(id).innerText;
      navigator.clipboard.writeText(texto).then(() => alert("Copiado: " + texto));
    }
  </script>
</body>
</html>
