<<template>
  <div class="container">

    <div class="left-panel">

      <div class="brand">

  <img
  src="./colores.png"
  alt="UNIVAC ERP"
  class="logo-univac"
/>
  <h2>Gestión Empresarial Inteligente</h2>

  <p>
    Plataforma integral para la administración
    y control de procesos empresariales.
  </p>

   </div>

    </div>

    <div class="right-panel">
        <div class="top-bar">
    <a
      href="https://clustersanfrancisco.com.ar/"
      target="_blank"
      class="btn-info"
    >
      Acerca de UNIVAC
    </a>
  </div>


      <div class="login-card">

        <h3>Iniciar Sesión</h3>

        <p class="welcome">
          Ingrese sus credenciales para continuar
        </p>

        <form @submit.prevent="login">

          <div class="form-group">
            <label>N° Documento</label>
            <input
              v-model="documento"
              type="text"
              placeholder="Ingrese su documento"
            >
          </div>

          <div class="form-group">
            <label>Usuario</label>
            <input
              v-model="usuario"
              type="text"
              placeholder="Ingrese su usuario"
            >
          </div>

          <div class="form-group">
            <label>Contraseña</label>
            <input
              v-model="clave"
              type="password"
              placeholder="Ingrese su contraseña"
            >
          </div>

          <button type="submit">
            Acceder al Sistema
          </button>

          <div
            v-if="mensaje"
            class="mensaje"
            :class="tipoMensaje"
          >
            {{ mensaje }}
          </div>

        </form>

      </div>
    </div>
  </div>

  <footer class="footer">
  <p>© 2026 Cluster Tecnológico San Francisco. Todos los derechos reservados.</p>
  <span>San Francisco, Córdoba, Argentina</span>
</footer>

</template>

<script setup>
import { ref } from 'vue'

const documento = ref('')
const usuario = ref('')
const clave = ref('')

const mensaje = ref('')
const tipoMensaje = ref('')

const login = () => {

  if (!documento.value.trim()) {
    mensaje.value = 'Debe ingresar el número de documento.'
    tipoMensaje.value = 'error'
    return
  }

  if (!usuario.value.trim()) {
    mensaje.value = 'Debe ingresar el usuario.'
    tipoMensaje.value = 'error'
    return
  }

  if (!clave.value.trim()) {
    mensaje.value = 'Debe ingresar la contraseña.'
    tipoMensaje.value = 'error'
    return
  }

  if (
    documento.value === '12345678' &&
    usuario.value === 'admin' &&
    clave.value === '1234'
  ) {

    mensaje.value = 'Acceso concedido. Bienvenido al sistema.'
    tipoMensaje.value = 'success'

  } else {

    mensaje.value = 'Los datos ingresados no coinciden con ningún usuario registrado del sistema.'
    tipoMensaje.value = 'error'

  }

}
</script>

<style scoped>

.right-panel{
    position: relative;
}

.btn-info{
    position: absolute;
    top: 35px;
    right: 45px;

    padding: 12px 24px;

    border: 2px solid #E43629;
    border-radius: 10px;

    color: #232B53;
    background: white;

    text-decoration: none;
    font-weight: 600;
    font-size: 15px;

    transition: .2s;
}

.btn-info:hover{
    background: #232B53;
    color: white;
}
.logo-univac{
    width: 900px;
    max-width: 100%;
    height: auto;
    display: block;
    margin-bottom: 35px;
}
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap');

*{
  font-family:'Montserrat', sans-serif;
}

html,
body{
    margin:0;
    padding:0;
    overflow-x:hidden;
}
.page{
    height:calc(100vh - 90px);
    display:flex;
    flex-direction:column;
}

.container{
    flex:1;
    display:flex;
    min-height:calc(100vh - 90px); 
}

.left-panel{
  background:
  linear-gradient(
    135deg,
    #232B53,
    #3157A3
  );

  display:flex;
  align-items:center;
  justify-content:center;

  padding:80px;
}

.brand{
  max-width:550px;
  color:white;
}

.logo-univac{
  width:320px;
  margin-bottom:40px;
}

.brand h1{
  font-size:56px;
  font-weight:700;
  margin-bottom:15px;
}

.brand h2{
  font-size:28px;
  font-weight:500;
  color:#6BB1E2;
  margin-bottom:25px;
}

.brand p{
  font-size:16px;
  line-height:1.8;
  color:#E5E7EB;
}

.brand a{
  display:inline-block;
  margin-top:30px;

  color:white;
  text-decoration:none;

  border:2px solid rgba(255,255,255,.3);
  border-radius:8px;

  padding:12px 24px;

  transition:.3s;
}

.brand a:hover{
  background:white;
  color:#232B53;
}

.right-panel{
  width:600px;

  display:flex;
  justify-content:center;
  align-items:center;

  padding:60px;
}

.login-card{
  width:100%;
  max-width:450px;
}

.login-card h3{
  color:#232B53;
  font-size:38px;
  font-weight:700;
  margin-bottom:10px;
}

.welcome{
  color:#6b7280;
  margin-bottom:35px;
  font-size:15px;
}

.form-group{
  margin-bottom:20px;
}

.form-group label{
  display:block;
  margin-bottom:8px;

  color:#232B53;

  font-size:14px;
  font-weight:600;
}

.form-group input{
  width:100%;

  padding:16px;

  border:1px solid #d1d5db;
  border-radius:10px;

  font-size:15px;

  transition:.2s;
}

.form-group input:focus{
  outline:none;

  border-color:#6BB1E2;

  box-shadow:
  0 0 0 3px rgba(107,177,226,.2);
}

button{
  width:100%;

  padding:16px;

  border:none;
  border-radius:10px;

  background:#232B53;

  color:white;

  font-size:15px;
  font-weight:600;

  cursor:pointer;

  transition:.3s;
}

button:hover{
  background:#3157A3;
}

.mensaje{
  margin-top:20px;
  padding:14px;
  border-radius:10px;
  font-size:14px;
  text-align:center;
}

.success{
  background:#ecfdf5;
  color:#166534;
}

.error{
  background:#fef2f2;
  color:#b91c1c;
}

@media(max-width:1000px){

  .container{
    flex-direction:column;
  }

  .left-panel{
    padding:50px;
  }

  .right-panel{
    width:100%;
    padding:40px;
  }

  .brand h1{
    font-size:42px;
  }

  .login-card h3{
    font-size:30px;
  }
}
.footer{
    width:100%;
    background:#232B53;
    color:white;
    text-align:center;
    padding:18px 10px;
    font-size:14px;
    line-height:1.5;
    border-top:1px solid #232B53;
}

.footer p{
    margin:0;
    font-weight:600;
}

.footer span{
    display:block;
    color:#C8D3E3;
    font-size:13px;
}

</style>
