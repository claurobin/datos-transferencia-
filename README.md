<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="robots" content="noindex, nofollow">
  <title>Datos de Transferencia</title>
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
    #btn {
      display: block; width: 100%; margin-top: 22px; padding: 14px;
      font-size: 1rem; font-weight: bold; color: #fff; background: #1a3c7a;
      border: none; border-radius: 8px; cursor: pointer;
    }
    #btn:active { background: #12295a; }
  </style>
</head>
<body>
  <div class="card">
    <h1>Datos para Transferencia</h1>

    <div class="row"><div class="label">Titular</div><div class="value">CLAUDIA ROBIN GONZALEZ</div></div>
    <div class="row"><div class="label">Banco</div><div class="value">Banco de Chile</div></div>
    <div class="row"><div class="label">Tipo de cuenta</div><div class="value">Cuenta Corriente</div></div>
    <div class="row"><div class="label">N.º de cuenta</div><div class="value">2500076703</div></div>
    <div class="row"><div class="label">RUT</div><div class="value">12592827-7</div></div>
    <div class="row"><div class="label">Correo</div><div class="value">bingo2026oxford@gmail.com</div></div>

    <button id="btn" onclick="copiarTodo()">Copiar datos</button>
  </div>

  <script>
    const datos =
`CLAUDIA ROBIN GONZALEZ
Banco de Chile - Cuenta Corriente
N.º de cuenta: 2500076703
RUT: 12592827-7
Correo: bingo2026oxford@gmail.com`;

    function copiarTodo() {
      const btn = document.getElementById("btn");
      const ok = () => { btn.textContent = "¡Copiado!"; setTimeout(() => btn.textContent = "Copiar datos", 2000); };
      if (navigator.clipboard) {
        navigator.clipboard.writeText(datos).then(ok);
      } else {
        const t = document.createElement("textarea");
        t.value = datos; document.body.appendChild(t); t.select();
        document.execCommand("copy"); document.body.removeChild(t); ok();
      }
    }
  </script>
</body>
</html>
