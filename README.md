<html><head><base href="/" />

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Información del Comprador y Resumen de Compra</title>

<style>

body {

font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);

margin: 0; padding: 20px; min-height: 100vh; display: flex;

justify-content: center; align-items: center;

}



.container { background: white; padding: 30px; border-radius: 15px;

box-shadow: 0 10px 20px rgba(0,0,0,0.1); width: 100%;

max-width: 600px;

}



h1, h2 {

color: #2c3e50; text-align: center;

margin-bottom: 30px;

}



.form-group {

margin-bottom: 20px;

}



label {

display: block; margin-bottom: 5px; color: #34495e;

font-weight: 500;

}



input, select { width: 100%; padding: 10px;

 

border: 2px solid #ddd; border-radius: 8px; font-size: 16px;

transition: border-color 0.3s ease;

}



input:focus, select:focus { border-color: #3498db; outline: none;

}



button {

background-color: #3498db; color: white;

padding: 12px 20px; border: none;

border-radius: 8px; width: 100%;

font-size: 16px; cursor: pointer;

transition: background-color 0.3s ease;

}



button:hover {

background-color: #2980b9;

}



.success-message { display: none; color: #27ae60; text-align: center; margin-top: 20px;

}



.order-summary { margin-top: 30px; padding: 20px;

background-color: #f8f9fa; border-radius: 8px;

}



.order-summary h2 { color: #2c3e50; font-size: 1.5em;

margin-bottom: 20px;

}

 

.summary-item { display: flex;

justify-content: space-between; margin-bottom: 10px; padding: 5px 0;

border-bottom: 1px solid #ddd;

}



.total {

font-weight: bold; color: #2c3e50; font-size: 1.2em; margin-top: 15px;

}

</style>

</head>

<body>

<div class="container">

<h1>Información del Comprador y Resumen de Compra</h1>

<form id="buyerForm">

<div class="form-group">

<label for="nombre">Nombre Completo:</label>

<input type="text" id="nombre" name="nombre" required>

</div>



<div class="form-group">

<label for="email">Correo Electrónico:</label>

<input type="email" id="email" name="email" required>

</div>



<div class="form-group">

<label for="pais">País:</label>

<input type="text" id="pais" name="pais" required>

</div>



<div class="form-group">

<label for="ciudad">Ciudad:</label>

<input type="text" id="ciudad" name="ciudad" required>

</div>



<div class="form-group">

<label for="direccion">Dirección:</label>

<input type="text" id="direccion" name="direccion" required>

</div>

 

<div class="form-group">

<label for="telefono">Teléfono:</label>

<input type="tel" id="telefono" name="telefono" required>

</div>



<div class="order-summary">

<h2>Resumen de Compra</h2>

<div id="cartItems">

<div class="summary-item">

<span>Producto 1</span>

<span>$100.00</span>

</div>

<div class="summary-item">

<span>Producto 2</span>

<span>$150.00</span>

</div>

<div class="summary-item">

<span>Producto 3</span>

<span>$200.00</span>

</div>

</div>

<div class="summary-item total">

<span>Total a Pagar:</span>

<span id="totalAmount">$450.00</span>

</div>

</div>



<button type="submit">Confirmar Pedido</button>

</form>

<div id="successMessage" class="success-message">

¡Pedido confirmado exitosamente!

</div>

</div>



<script>

// Simulación de carrito de compras const cart = {

items: [

{ name: 'Producto 1', price: 100 },

{ name: 'Producto 2', price: 150 },

{ name: 'Producto 3', price: 200 }

],

total: 450

};



document.getElementById('buyerForm').addEventListener('submit', function(e) {

 

e.preventDefault();



// Recopilar datos del formulario const formData = {

nombre: document.getElementById('nombre').value, email: document.getElementById('email').value, pais: document.getElementById('pais').value, ciudad: document.getElementById('ciudad').value,

direccion: document.getElementById('direccion').value, telefono: document.getElementById('telefono').value, total: cart.total

};



// Aquí podrías enviar los datos a un servidor console.log('Datos del pedido:', formData);



// Mostrar mensaje de éxito

const successMessage = document.getElementById('successMessage'); successMessage.style.display = 'block';



// Limpiar el formulario this.reset();



// Ocultar el mensaje después de 3 segundos setTimeout(() => {

successMessage.style.display = 'none';

}, 3000);

});



// Validación básica del teléfono document.getElementById('telefono').addEventListener('input', function(e) {

this.value = this.value.replace(/[^0-9+\-\s]/g, '');

});



// Validación del email document.getElementById('email').addEventListener('blur', function(e) {

const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; if (!emailRegex.test(this.value)) {

this.setCustomValidity('Por favor, ingrese un correo electrónico válido');

} else {

this.setCustomValidity('');

}

});

</script>

</body></html>

