<script setup>
import { ref } from "vue";

const email = ref("");
const password = ref("");

const handleSubmit = () => {
  if (!email.value || password.value.length < 6) {
    return alert("Todos los campos son obligatorios y la contraseña debe tener al menos 6 caracteres.");
  }
  alert("¡Inicio de sesión exitoso!");
};
</script>

<template>
  <div class="container">
    <div class="form-container">
      <div class="form-content">
        <h5 class="form-title">Inicio de sesión</h5>
        <form @submit.prevent="handleSubmit" class="space-y-4">
          <div class="form-group">
            <input
              type="email"
              placeholder="Email"
              v-model.trim="email"
              class="input-field"
            />
          </div>
          <div class="form-group">
            <input
              type="password"
              placeholder="Contraseña"
              v-model.trim="password"
              class="input-field"
            />
          </div>
          <div class="form-group">
            <button type="submit" class="submit-button">Iniciar sesión</button>
          </div>
        </form>
      </div>
    </div>
  </div>

  <div class="footer">
    <p>© {{ new Date().getFullYear() }} IBS Consultores</p>
  </div>
</template>

<style scoped>
/* Contenedor principal */
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 0.75rem;
  margin-bottom: 0.5rem;
}

/* Caja principal del formulario */
.form-container {
  display: flex;
  flex-direction: column;
  background-color: #f7f7f7;
  border: 1px solid #e5e7eb;
  border-radius: 0.5rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 55rem;
  height: 40rem;
}

/* Formulario */
.form-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 1.5rem;
}

.form-title {
  margin-bottom: 2rem;
  font-size: 1.5rem;
  font-weight: bold;
}

.form-group {
  width: 100%;
}

.input-field {
  width: 100%;
  padding: 0.5rem 1rem;
  color: #4b5563;
  border: 1px solid #d1d5db;
  border-radius: 0.375rem;
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.input-field:focus {
  border-color: #3b82f6;
  box-shadow: 0 0 0 2px #3b82f6;
}

/* Boton de enviar */
.submit-button {
  width: 100%;
  padding: 0.5rem 1rem;
  color: white;
  background-color: #0F3785;
  border-radius: 0.375rem;
  outline: none;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-button:hover {
  background-color: #0F3775;
}

.submit-button:focus {
  box-shadow: 0 0 0 2px #3b82f6;
}

/* Pie de pagina */
.footer {
  margin-bottom: 0.5rem;
  margin-top: 0.125rem;
  text-align: center;
}
</style>
