<template>
  <div class="form-section">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      preserveAspectRatio="none"
      viewBox="0 0 1680 40"
      class="form__arch container__arch"
      style="transform: scaleY(-1)"
    >
      <path d="M0 40h1680V30S1340 0 840 0 0 30 0 30z" fill="#fff"></path>
    </svg>
    <section class="container">
      <h2>Shoot me a message!</h2>
      <form
        name="contact"
        method="post"
        data-netlify="true"
        data-netlify-honeypot="bot-field"
        data-netlify-recaptcha="true"
        class="form"
        enctype="application/x-www-form-urlencoded"
        @submit.prevent="handleFormSubmit"
      >
        <input type="hidden" name="form-name" value="contact" />
        <roke-input
          placeholder="Name"
          customId="name"
          :inputData.sync="formData.name"
          class="form__field--half"
        />
        <roke-input
          placeholder="E-Mail"
          customId="email"
          :inputData.sync="formData.email"
          type="email"
          class="form__field--half"
        />
        <roke-input
          placeholder="Nachricht"
          customId="message"
          :inputData.sync="formData.message"
          textarea
          class="form__field"
        />
        <div data-netlify-recaptcha="true"></div>
        <input type="submit" value="Nachricht senden" class="form__button" />
      </form>
    </section>
  </div>
</template>

<script>
import RokeInput from "@/components/shared/RokeInput";
import axios from "axios";

export default {
  name: "RokeForm",
  components: { RokeInput },
  data() {
    return {
      formData: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    encode(data) {
      const formData = new FormData();

      for (const key of Object.keys(data)) {
        formData.append(key, data[key]);
      }

      return formData;
    },
    handleFormSubmit(e) {
      const axiosConfig = {
        header: { "Content-Type": "application/x-www-form-urlencoded" },
      };

      axios
        .post(
          location.href,
          this.encode({
            "form-name": e.target.getAttribute("name"),
            ...this.formData,
          }),
          axiosConfig
        )
        .then((data) => console.log(data))
        .catch((error) => console.log(error))
        .then(() => alert("Danke!"));
    },
  },
};
</script>

<style lang="scss" scoped>
.form-section {
  position: relative;
  background: #f0daf8; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    110deg,
    #f0daf8,
    #ddf1fd,
    #f2f3fc
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    110deg,
    #f0daf8,
    #ddf1fd,
    #f2f3fc
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.form {
  display: flex;
  flex-wrap: wrap;

  &__field {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    &--half {
      @extend .form__field;
      width: 50%;
    }
  }

  &__button {
    font-size: 1.2rem;
    margin: 1.5rem auto 0;
    background-color: unset;
    border: none;
    border-radius: 0;
    color: #6252ba;
    font-weight: bold;
    padding: 10px 20px 5px;
    cursor: pointer;

    box-shadow: inset 0 -3px 0 -1px #6252ba;
    transition: box-shadow 0.15s ease-in-out, color 0.15s ease-in-out;
    line-height: 40px;

    &:hover {
      color: white;
      box-shadow: inset 0 -50px 0 -1px #6252ba;
    }
  }

  &__recaptcha {
    margin: 0 auto;
  }

  &__arch {
    top: 0;
    margin-top: -0.25rem;
  }
}
</style>
