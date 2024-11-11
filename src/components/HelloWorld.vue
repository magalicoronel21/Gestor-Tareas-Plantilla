<!-- Barra de navegación -->
<nav class="navbar">
  <ul>
    <li><a href="#home">Inicio</a></li>
    <li><a href="#about">Acerca de</a></li>
    <li><a href="#contact">Contacto</a></li>
  </ul>
</nav>

<!-- Contenido principal -->
<div class="custom-component">
  <h1>Bienvenido a Tu Proyecto</h1>
  <p>Descubre cómo puedes personalizar y configurar el proyecto a tu gusto.</p>
  
  <h3>Recursos Útiles</h3>
  <ul class="resource-links">
    <li><a href="https://example.com" target="_blank" rel="noopener">Documentación</a></li>
    <li><a href="https://example.com/community" target="_blank" rel="noopener">Comunidad</a></li>
    <li><a href="https://example.com/support" target="_blank" rel="noopener">Soporte</a></li>
    <li><a href="https://example.com/news" target="_blank" rel="noopener">Noticias</a></li>
  </ul>
  
  <!-- Botón interactivo -->
  <button class="primary-button" onclick="alert('Gracias por visitar nuestro proyecto!')">Saber más</button>
</div>

<!-- Footer -->
<footer class="footer">
  <p>&copy; 2024 Mi Proyecto. Todos los derechos reservados.</p>
</footer>

<style>
/* Fondo degradado de la página */
body {
  background: linear-gradient(135deg, #74ebd5 0%, #acb6e5 100%);
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Barra de navegación */
.navbar {
  background-color: #333;
  padding: 10px 0;
  text-align: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
}

.navbar ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: inline-flex;
  gap: 20px;
}

.navbar a {
  color: #fff;
  text-decoration: none;
  font-size: 18px;
  padding: 8px 16px;
  transition: background-color 0.3s;
}

.navbar a:hover {
  background-color: #42b983;
  border-radius: 4px;
}

/* Estilos principales del contenedor */
.custom-component {
  width: 80%;
  max-width: 800px;
  margin: 20px auto;
  padding: 30px;
  background-color: #ffffff;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
  text-align: center;
  flex: 1;
}

.custom-component h1 {
  font-size: 32px;
  color: #42b983;
  margin-bottom: 15px;
}

.custom-component p {
  font-size: 18px;
  color: #555;
  margin-bottom: 25px;
}

.custom-component h3 {
  font-size: 22px;
  color: #333;
  margin-top: 25px;
  border-bottom: 2px solid #42b983;
  display: inline-block;
  padding-bottom: 6px;
}

/* Estilos para los enlaces */
.resource-links {
  list-style-type: none;
  padding: 0;
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

.resource-links li {
  margin: 15px 0;
}

.resource-links a {
  font-size: 18px;
  color: #42b983;
  text-decoration: none;
  background-color: #e8f5e9;
  padding: 10px 20px;
  border-radius: 8px;
  transition: background-color 0.3s, color 0.3s;
}

.resource-links a:hover {
  background-color: #42b983;
  color: #fff;
}

/* Estilo del botón */
.primary-button {
  font-size: 18px;
  color: #ffffff;
  background-color: #42b983;
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s;
  margin-top: 20px;
}

.primary-button:hover {
  background-color: #333;
}

/* Footer */
.footer {
  background-color: #333;
  color: #ffffff;
  text-align: center;
  padding: 15px 0;
  font-size: 16px;
}
</style>




