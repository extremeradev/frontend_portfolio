<template>
    <section id="contact">
        <div class="px-4 xl:pl-16 mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="flip-right">
            <h2 class="text-4xl font-bold text-white text-left mb-4">Cont<span
                    class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">acto</span>
            </h2>
            <form class="w-full" id="contact-form" @submit.prevent="sendEmail">
                <div class="w-full mb-4 max-w-[290px] md:max-w-[100px] lg:max-w-[500px] xl:max-w-[700px]">
                    <label for="name" class="block mb-2 text-white">Empresa</label>
                    <input v-model="email.subject" type="text" id="name" class="w-full p-3 bg-gray-300 text-[#111a3e] rounded-md" required />
                </div>
                <div class="w-full mb-4 max-w-[290px] md:max-w-[100px] lg:max-w-[500px] xl:max-w-[700px]">
                    <label for="message" class="block mb-2 text-white">Mensaje</label>
                    <textarea v-model="email.text" id="message" rows="4" class="w-full p-3 bg-gray-300 text-[#111a3e] rounded-md"
                        required></textarea>
                </div>
                <div class="w-4/4">
                    <button type="submit"
                    class="w-full mb-4 max-w-[70px] sm:max-w-[100px] md:max-w-[100px] lg:max-w-[100px] xl:max-w-[120px] bg-primary p-3 text-[#111a3e] font-semibold rounded-md hover:bg-primary-dark">Enviar</button>
                </div>
            </form>
        </div>
    </section>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      email: {
        subject: "",
        text: "",
      },
    };
  },
  methods: {
    async sendEmail() {
      try {
        const response = await axios.post("https://backend-portfolio-wprm.onrender.com/send-email", {
          subject: this.email.subject,
          text: this.email.text,
          html: `<p>${this.email.text}</p>`, // Convertimos el texto a HTML
        });
        alert("Correo enviado: " + response.data.messageId);
      } catch (error) {
        console.error("Error enviando correo:", error);
        alert("Hubo un error al enviar el correo.");
      }
    },
  },
};

</script>