<template>
  <section id="contact">
    <div
      class="px-4 xl:pl-16 mt-4 md:mt-0 text-left flex flex-col z-10 h-full"
      data-aos="flip-right"
    >
      <div class="flex">
        <h2 class="text-4xl font-bold text-[#2C2C2C] text-left mb-4">Contacto</h2>
        <div class="w-1/4 ml-2 relative bottom-1">
          <img
            @click="redirectToLinkedin"
            src="https://img.icons8.com/ios-glyphs/60/2c2c2c/linkedin.png"
            class="cursor-pointer hover:filter hover:brightness-200 transition-all"
          />
        </div>
      </div>

      <!-- Formulario de contacto -->
      <form
        class="w-full"
        id="contact-form"
        @submit.prevent="sendEmail"
      >
        <div
          class="w-full mb-4 max-w-[290px] md:max-w-[100px] lg:max-w-[500px] xl:max-w-[700px]"
        >
          <label
            for="name"
            class="block mb-2 text-[#2C2C2C] font-semibold"
            >Empresa</label
          >
          <input
            v-model="email.subject"
            type="text"
            id="name"
            class="w-full p-3 bg-gray-300 text-[#2C2C2C] rounded-md"
            required
          />
        </div>
        <div
          class="w-full mb-4 max-w-[290px] md:max-w-[100px] lg:max-w-[500px] xl:max-w-[700px]"
        >
          <label
            for="message"
            class="block mb-2 text-[#2C2C2C] font-semibold"
            >Mensaje</label
          >
          <textarea
            v-model="email.text"
            id="message"
            rows="4"
            class="w-full p-3 bg-gray-300 text-[#2C2C2C] rounded-md"
            required
          ></textarea>
        </div>
        <div class="w-4/4 flex">
          <button
            type="submit"
            :disabled="isLoading"
            class="w-full relative top-1.5 mb-4 max-w-[110px] sm:max-w-[130px] md:max-w-[100px] lg:max-w-[100px] xl:max-w-[120px] bg-[#7F6A9D] p-3 text-white font-semibold rounded-md hover:bg-primary-dark disabled:opacity-50"
          >
            {{ isLoading ? "Enviando..." : "Enviar" }}
          </button>
        </div>
      </form>
    </div>

    <!-- Loading spinner con fondo gris en todo el body -->
    <div
      v-if="isLoading"
      class="fixed inset-0 flex items-center justify-center bg-gray-700 bg-opacity-70 z-50"
    >
      <div
        class="animate-spin w-12 h-12 border-4 border-white border-t-transparent rounded-full"
      ></div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import Swal from "sweetalert2";

export default {
  mounted() {
    // Establece el scroll en la parte superior de la página cuando el componente se monta
    window.scrollTo(0, 0);
  },
  data() {
    return {
      email: {
        subject: "",
        text: "",
      },
      isLoading: false, // Estado para controlar el loading
    };
  },
  methods: {
    redirectToLinkedin() {
      window.open("https://www.linkedin.com/in/alejandro-lopez-extremera/");
    },
    async sendEmail() {
      this.isLoading = true; // Activar el spinner
      try {
        const response = await axios.post(
          "https://backend-portfolio-wprm.onrender.com/send-email",
          {
            subject: this.email.subject,
            text: this.email.text,
            html: `<p>${this.email.text}</p>`, // Convertimos el texto a HTML
          }
        );
        // Mostrar un mensaje estiloso de éxito
        Swal.fire({
          icon: "success",
          title: "¡Correo enviado!",
          text: `Tu mensaje fue enviado correctamente`,
          confirmButtonColor: "#7F6A9D", // Personaliza el color del botón
        }).then( () => {
          window.location.reload();
        });
        
      } catch (error) {
        console.error("Error enviando correo:", error);
        Swal.fire({
          icon: "error",
          title: "¡Error!",
          text: "Hubo un problema al enviar el correo. Por favor, inténtalo nuevamente.",
          confirmButtonColor: "#FF6B6B", // Personaliza el color del botón
        });
      } finally {
        this.isLoading = false; // Desactivar el spinner
      }
    },
  },
};
</script>