<template>
  <div class="form-section">
    <section class="container">
      <h2>Shoot me a message!</h2>
      <form action="POST" data-netlify="true" class="form">
        <roke-input
          placeholder="Name"
          v-model="name"
          class="form__field--half"
        />
        <roke-input
          placeholder="E-Mail"
          v-model="email"
          type="email"
          class="form__field--half"
        />
        <roke-input
          placeholder="Nachricht"
          v-model="message"
          textarea
          class="form__field"
        />
        <div data-netlify-recaptcha="true" class="form__recaptcha"></div>
        <input type="submit" value="Nachricht senden" class="form__button" />
      </form>
    </section>
  </div>
</template>

<script>
import RokeInput from "@/components/shared/RokeInput";
export default {
  name: "RokeForm",
  components: { RokeInput },
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.form-section {
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
    color: #6252BA;
    font-weight: bold;
    padding: 10px 20px 5px;
    cursor: pointer;

    box-shadow: inset 0 -3px 0 -1px #6252BA;
    transition: box-shadow 0.15s ease-in-out, color 0.15s ease-in-out;
    line-height: 40px;

    &:hover {
      color: white;
      box-shadow: inset 0 -50px 0 -1px #6252BA;
    }
  }

  &__recaptcha {
    margin: 0 auto;
  }
}
</style>
