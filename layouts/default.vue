<template>
  <v-app>
      <v-app-bar color="#ffffff" app width="100%" height="100px">
        <v-img :src="require('~/assets/img/logo.png')" class="logo1v"></v-img>
        <v-spacer></v-spacer>
        <v-btn class="nav" href="#inicio" elevation="0">Inicio</v-btn>
        <v-btn class="nav" href="#productos" elevation="0">Productos</v-btn>
        <v-btn class="nav" href="#nosotros" elevation="0">Nosotros</v-btn>
        <v-btn class="nav" href="#contactanos" elevation="0">Contáctanos</v-btn>
        <v-spacer></v-spacer>
      </v-app-bar>
    

    <div style="margin-bottom: 60px;" id="inicio"></div>
    <div class="paaginaweb123">
      <v-container fluid class="background-container" >
        <v-row justify="center">
          <v-col cols="12" md="6" class="text-left">
            <div class="space-y-4">
              <br />
              <h1 class="h1w text-4xl font-bold h1blanco">VanyxTech</h1>
              <br />
              <h2 class="h2w text-white text-2xl text-custom-color">
                Donde la tecnología se une al juego.
              </h2>
              <br />
              <p class="pw text-white">
                Descubre una amplia selección de componentes y periféricos de PC
                para mejorar tu experiencia de juego y productividad. Desde
                procesadores de última generación hasta accesorios gaming de alta
                calidad, estamos aquí para ofrecerte lo mejor en tecnología.
                ¡Únete a nosotros y lleva tu setup al siguiente nivel!
              </p>
            </div>
          </v-col>
          <v-col cols="12" md="6" class="new-text-center">
            <v-img
              src="https://i.pinimg.com/564x/dd/f9/cb/ddf9cbeb8a710c7174eb93e804e2e066.jpg"
              alt="Gaming PC Setup"
              class="rounded-lg shadow-lg"
              style="max-width: 600px; max-height: 700px; margin-left: 150px"
            ></v-img>
          </v-col>
        </v-row>
      </v-container>
      <div style="margin-bottom: 60px;" id="productos"></div>
      <br>

<v-container>
  <h1 class="Tproduc">Nuestros Productos:</h1>
  <v-row justify="center">
    <v-col
      v-for="(product, index) in visibleProducts"
      :key="index"
      cols="12"
      sm="6"
      md="4"
    >
      <v-card color="white" outlined>
        <v-carousel
          cycle
          hide-delimiters
          v-model="product.currentImageIndex"
          v-show="product.images.length > 1"
        >
          <v-carousel-item
            v-for="(image, imgIndex) in product.images"
            :key="imgIndex"
          >
            <v-img
              width="300px"
              height="300px"
              :src="image"
              contain
            ></v-img>
          </v-carousel-item>
        </v-carousel>
        <v-card-title class="blue--text text--darken-3 custom-card-title">{{
          product.name
        }}</v-card-title>
        <v-card-subtitle class="grey--text text--darken-2">{{
          product.price
        }}</v-card-subtitle>
        <v-card-actions>
          <v-btn
            color="#002E60"
            dark
            text
            @click="toggleDescription(product)"
            rounded
          >
            {{ product.showDescription ? "Ocultar" : "Descripción" }}
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn color="#002E60" dark @click="buy(product)" rounded>
            Comprar
          </v-btn>
        </v-card-actions>
        <v-expand-transition>
          <div
            class="blue--text text--darken-3"
            v-show="product.showDescription"
          >
            <v-divider></v-divider>
            <v-card-text>{{ product.description }}</v-card-text>
          </div>
        </v-expand-transition>
      </v-card>
    </v-col>
  </v-row>
  <v-row justify="center">
    <v-btn color="#002E60" dark @click="toggleShowMore" rounded>
      {{ showMoreText }}
    </v-btn>
  </v-row>
</v-container>

      <br><br>
      <div style="margin-bottom: 60px;" id="nosotros"></div>
      <br>
      <v-container fluid class="new-background-container" >
        <v-row justify="center">
          <v-col cols="12" md="6" class="new-text-right">
            <v-img
              src="https://fiverr-res.cloudinary.com/images/q_auto,f_auto/gigs/305778276/original/dbe45f7db09d9bb96df9ce7da72e138f5da66525/pick-out-pc-parts-for-a-certain-budget.jpg"
              alt="Gaming PC Setup"
              class="new-rounded-lg new-shadow-lg"
              style="max-width: 120%; max-height: auto; margin-left: 10px"
            ></v-img>
          </v-col>
          <v-col cols="12" md="6" class="new-text-center">
            <div class="space-y-4">
              <br />
              <h1 class="Nosotros new-text-4xl new-font-bold">Nosotros</h1>
              <br />
              <br />
              <p class=" pw new-text-white">
                En VanyxTech, estamos obsesionados con los videojuegos y la
                tecnología. Fundada por apasionados de la industria, nos
                dedicamos a ofrecer productos de alta calidad que mejoren tu
                experiencia de juego. Desde consolas hasta periféricos de PC,
                estamos aquí para llevarte al siguiente nivel. ¡Únete a nosotros
                y descubre el mundo de VanyxTech!
              </p>
            </div>
          </v-col>
        </v-row>
      </v-container>
      <br><br>
      <div style="margin-bottom: 60px;" id="contactanos"></div>
      <br>
      <v-container >
        <h1 class="Tproduc">Contactanos</h1>
        <p class="Contacp">
          ¿Tienes alguna pregunta, sugerencia o simplemente quieres saludarnos?
          <br />
          ¡Estamos aquí para ayudarte! Completa el formulario a continuación y
          nos pondremos en contacto contigo lo antes posible.
        </p>
        <v-row justify="center">
          <v-col cols="12" md="6" class="new-text-right">
            <v-img
              :src="require('~/assets/img/Contactanos.png')"
              alt="Gaming PC Setup"
              class="new-rounded-lg new-shadow-lg"
              style="max-width: 80%; max-height: auto; margin-left: 10px"
            ></v-img>
          </v-col>

          <v-col cols="12" md="6">
            <v-form class="paaginaweb123">
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Nombre"
                required
              ></v-text-field>

              <v-text-field
                v-model="email"
                :rules="emailRules"
                label="Correo Electrónico"
                required
              ></v-text-field>

              <v-textarea
                v-model="message"
                :rules="messageRules"
                label="Mensaje"
                required
              ></v-textarea>

              <v-btn
                color="#002E60"
                dark
                :disabled="!valid"
                @click="submitForm"
                rounded
              >
                Enviar
              </v-btn>
            </v-form>
          </v-col>
        </v-row>
      </v-container>

      <template>
        <v-footer class="footer" color="#002e60">
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
      
          <!-- Parte central del footer-->
          <v-col cols="12" md="4" class="text-center">
            <div class="space-y-2">
              <p class="white--text">
                Dirección: Calle Dos Sur, San José Valsequillo, Tlacotepec de
                Benito Juárez, Puebla, México
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
      
          <!-- Iconos de la derecha-->
          <v-col cols="14" md="4" class="text-right">
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
        </v-footer>
      </template>
      
    </div>


  </v-app>
</template>>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      products: [
        {
          name: "Asus ROG Keris Wireless Gaming Mouse Black",
          images: [
            require("~/assets/img/mouse/Producto1M.png"),
            require("~/assets/img/mouse/mouse2.jpg"),
            require("~/assets/img/mouse/mouse3.jpg"),
            require("~/assets/img/mouse/mouse4.jpg"),
          ],
          price: "$500 MXN",
          description:
            "El Asus ROG Keris Ratón Inalámbrico para Juegos Negro ofrece un diseño ergonómico, tecnología inalámbrica avanzada, sensor óptico preciso, switches mecánicos duraderos, iluminación RGB personalizable y compatibilidad versátil con sistemas operativos y juegos.",
          showDescription: false,
        },

        {
          name: "Mando Xbox Wireless Verde Electric Volt",
          images: [
            require("~/assets/img/mandoxbox/mando.jpg"),
            require("~/assets/img/mandoxbox/mando2.jpg"),
            require("~/assets/img/mandoxbox/mando3.jpg"),
            require("~/assets/img/mandoxbox/mando4.jpg"),
            require("~/assets/img/mandoxbox/mando5.jpeg"),
          ],
          price: "$799 MXN",
          description:
            "El Mando Xbox Wireless Verde Electric Volt es un controlador inalámbrico para Xbox Series X, Xbox One y Xbox One S, con un vibrante color verde eléctrico volt. Ofrece conectividad inalámbrica, botones estándar de Xbox, y un diseño ergonómico para una experiencia de juego cómoda y sin cables.",
          showDescription: false,
        },

        {
          name: "Laptop ASUS ROG Zephyrus G16k",
          images: [
            require("~/assets/img/laptop/laptop.png"),
            require("~/assets/img/laptop/laptop2.jpg"),
            require("~/assets/img/laptop/laptop3.jpg"),
            require("~/assets/img/laptop/laptop4.jpg"),
          ],
          price: "$14,000 MXN",
          description:
            'Procesador: Intel Core i7-12700H\nTarjeta gráfica: NVIDIA GeForce RTX 4050 (portátil, 120 W)\nPantalla: 16.0" WUXGA (1920 x 1200), 165 Hz, IPS + G-Sync\nAlmacenamiento: SSD de 512 GB\nMemoria: DDR4 de 16 GB\nPeso: 2,00 kg (4,4 libras)',
          showDescription: false,
        },
        {
          name: "NVIDIA GeForce RTX 4090",
          images: [
            require("~/assets/img/grafica/grafica.jpg"),
            require("~/assets/img/grafica/grafica2.jpg"),
            require("~/assets/img/grafica/grafica3.jpg"),
            require("~/assets/img/grafica/grafica4.jpg"),
          ],
          price: "$14,999",
          description:
            "Procesador de gráficos: NVIDIA GeForce RTX 4090\nRAM para gráficos: 24 GB\nVelocidad GPU: 2,52 GHz\n16,384 NVIDIA CUDA Cores\nSoporte 4K 120Hz HDR, 8K 60Hz HDR\nNuevo multiprocesadores de transmisión\n4 Núcleos tensor\nNúcleos RT de tercera generación\nRendimiento acelerado por IA: NVIDIA DLSS 3\nPlataforma de baja latencia NVIDIA Reflex\nTransmisión en vivo: NVIDIA Encoder\n8K HDR",
          showDescription: false,
        },
        {
          name: "Intel Core i5-13400F",
          images: [
            require("~/assets/img/procesador/procesadorIntel.jpg"),
            require("~/assets/img/procesador/procesadorIntel2.jpg"),
            require("~/assets/img/procesador/procesadorIntel3.jpg"),
            require("~/assets/img/procesador/procesadorIntel4.jpg"),
          ],
          price: "$3,399",
          description:
            "Procesador: Intel Core i5-13400F\nVelocidad de la CPU: Hasta 4,60 GHz\nMarca: Intel\nModelo de CPU: Núcleo i5\nZócalo de CPU: FCLGA1700",
          showDescription: false,
        },
        {
          name: "Monitor Lenovo G27qc-30",
          images: [
            require("~/assets/img/monitor/monitor.jpeg"),
            require("~/assets/img/monitor/monitor2.jpeg"),
            require("~/assets/img/monitor/monitor3.jpeg"),
            require("~/assets/img/monitor/monitor4.jpeg"),
            require("~/assets/img/monitor/monitor5.jpeg"),
          ],
          price: "$999",
          description:
            "Monitor Lenovo G27qc-30\nTamaño: 27 pulgadas\nFrecuencia de actualización: 165Hz\nRelación de aspecto: 16:9",
          showDescription: false,
        },
        
      ],
      showMore: false,
      currentImageIndex: 0, // imagen cero donde va iniciar 
    };
  },
  computed: {
    visibleProducts() {
      return this.showMore ? this.products : this.products.slice(0, 3);
    },
    showMoreText() {
      return this.showMore ? "Mostrar menos" : "Ver más";
    },
  },
  methods: {
    toggleDescription(product) {
      product.showDescription = !product.showDescription;
    },
    buy(product) {
      window.open(
        `https://api.whatsapp.com/send?phone=NUMERO&text=Hola%2C%20me%20interesa%20comprar%20el%20producto%20${encodeURIComponent(
          product.name
        )}`,
        "_blank"
      );
    },
    toggleShowMore() {
      this.showMore = !this.showMore;
    },
    // Cambiar imagen
    startCarousel() {
      setInterval(() => {
        this.currentImageIndex =
          (this.currentImageIndex + 1) % this.products[0].images.length;
      }, 3000); 
    },
  },
  mounted() {
    this.startCarousel(); 
  },
};
</script>

<style lang="scss">
.text-custom-color {
  color: $custom-color;
}

.ProducTitu {
  text-align: center;
  color: #002e60;
}
.background-container {
  background-image: url("~assets/img/inicio1.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover; 
  width: 100%;
  height: 90vh; 
}

.paaginaweb123 {
  background-color: #ffffff;
}

.TituloW {
  color: #ffffff;
}
.subTi {
  color: #00c8b6;
}
.contenido {
  text-align: left;
  flex: 1;
  padding-right: 45%;
}
.imagen-derecha {
  margin-left: 60px;
  margin-top: 10px;
}
.imagen-derecha img {
  width: 90%;
  padding-left: 60%;
  margin-top: 10px;
}

.new-background-container {
  background-image: url(../assets/img/fondo2.png);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover; 
  width: 100%;
  height: 70vh; 
}
.custom-card-title {
  margin-top: -10.5rem;
}
.new-text-right {
  text-align: right;
}

.new-text-center {
  text-align: center !important;
}

.new-text-white {
  color: #ffffff !important;
}

.new-text-custom-color {
  color: #007bff !important; /* Puedes ajustar el color personalizado según sea necesario */
}

.new-font-bold {
  font-weight: bold !important;
}

.new-rounded-lg {
  border-radius: 1rem;
}

.new-shadow-lg {
  box-shadow: 0px 4px 6px rgb(0, 200, 182);
}
.Nosotros {
  color: #00c8b6;
  font-size: 3rem;

}


.Contacp {
  color: #002e60;
  text-align: center;
  font-size: 1.5rem;

}
.imagenSoport {
  width: 40%;
  height: auto;
}
.Tproduc {
  color: #002e60;
  text-align: center;
  font-size: 3rem;
}
.footer {
  text-align: center;
}
.float-left {
  text-align: left;
}
.logof {
  width: 120px;
  text-align: right;
}


.logo1v {
  max-width: 130px; 
  max-height: 90px; 
  width: auto; 
  height: auto; 
}

.nav {
  background-color: #ffffff !important;
  margin-right: 24px;
  color: #007bff !important;
  transition: color 0.3s; 
}
.h1blanco{
  color: #ffffff;
  font-size: 6rem;
}
.h2w{
  font-size: 3rem;

}
.pw{
  font-size: 1.5rem;
  color: #ffffff;

 
}
.icon-large {
  font-size: 24px; 
  margin-right: 10px;
}
@media only screen and (max-width: 600px) {
  .nav {
    font-size: 0.1px;
    padding: 0.1px 0.1px;
    margin-bottom: 1px;
  }
  .logo1v {
    max-width: 10px;
    max-height: 20px;
  }
  .h1w {
    font-size: 2rem;
  }
  .h2w {
    font-size: 1.5rem;
  }
  .pw {
    font-size: 0.8rem;
  }
  .rounded-lg {
    max-width: 300px;
    max-height: 350px;
    text-align: center;
  }
}

@media only screen and (min-width: 601px) and (max-width: 1024px) {
  .nav {
    font-size: 16px;
  }
}



</style>

