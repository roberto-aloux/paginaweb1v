<template>
    <v-footer class="footer" color="#002e60">
      <v-container>
        <!-- Contenido del footer -->
        <v-row>
          <!-- Sección de contacto -->
          <v-col cols="12" md="4" class="text-left">
            <div class="space-y-2">
              <h5 class="font-bold white--text">Contacto</h5>
              <p class="font-bold white--text">
                <i class="fas fa-phone-alt"></i> 000-000-0000
              </p>
              <p class="font-bold white--text">
                <i class="fab fa-whatsapp"></i> Whatsapp
              </p>
              <p class="font-bold white--text">
                <i class="fas fa-envelope"></i> VanxyTech@gmail.com
              </p>
              <p class="font-bold white--text">
                <i class="fas fa-calendar-alt"></i> Lunes a Sábados 09:00 a 20:00 horas
              </p>
            </div>
          </v-col>
          
          <!-- Sección central del footer -->
          <v-col cols="12" md="4" class="text-center">
            <div class="space-y-2">
              <p class="white--text">
                Dirección: Calle Dos Sur, San José Valsequillo, Tlacotepec de Benito Juárez, Puebla, México
              </p>
              <p class="white--text">
                ¡Nos encantaría verte en nuestras instalaciones en VanxyTech!
              </p>
              <v-img
                :src="require('~/assets/img/icono2.png')"
                alt="Gaming Controller Icon"
                class="logof ml-auto mr-auto"
                align="center"
              ></v-img>
            </div>
          </v-col>
          
          <!-- Sección de redes sociales -->
          <v-col cols="12" md="4" class="text-right">
            <div class="space-y-2">
              <h5 class="font-bold white--text">Redes Sociales</h5>
              <div class="flex space-x-4">
                <a href="https://www.facebook.com/" target="_blank" class="white--text">
                  <i class="fab fa-facebook-f icon-large" style="color: #ffffff"></i>
                </a>
                <a href="https://www.instagram.com/" target="_blank" class="white--text">
                  <i class="fab fa-instagram icon-large"></i>
                </a>
                <a href="https://x.com/X" target="_blank" class="white--text">
                  <i class="fab fa-twitter icon-large white--text"></i>
                </a>
                <a href="https://www.youtube.com/" target="_blank" class="white--text">
                  <i class="fab fa-youtube icon-large"></i>
                </a>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </template>
  
  <script>
  export default {
  };
  </script>
  
  <style scoped>
  /* Estilos para el componente <v-footer> */
  .footer {
    text-align: center;
  }
  
  .space-y-2 {
    margin-bottom: 1rem;
  }
  
  .font-bold {
    font-weight: bold;
  }
  
  .white--text {
    color: #ffffff;
  }
  
  .icon-large {
    font-size: 24px;
    text-align: center;
  }
  
  .flex {
    display: flex;
  }
  
  .space-x-4 {
    justify-content: space-between;
  }
  
  .logof {
    width: 120px;
    text-align: center;
  }
  
  /* Media query para dispositivos móviles */
  @media only screen and (max-width: 600px) {
    .text-left,
    .text-center,
    .text-right {
      text-align: center !important;
    }
  
    .icon-large {
      font-size: 20px; /* Ajustar tamaño de iconos para dispositivos móviles */
    }
  }
  </style>
  