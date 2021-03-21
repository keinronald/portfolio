<template>
  <div>
    <div class="input__wrapper">
      <input
        v-if="!textarea"
        class="input"
        :type="type"
        :name="customId"
        :id="customId"
        required="required"
        @change="checkInput"
        :value="inputData"
        @input="$emit('update:inputData', $event.target.value)"
      />
      <label
        :for="customId"
        class="input__placeholder"
        :class="{ 'input__placeholder--top': inputData !== '' }"
      >
        {{ placeholder }}
      </label>
      <textarea v-if="textarea" :name="customId" :id="customId" rows="3"
                placeholder="Your Message"
                class="input"
                required="required"
                :value="inputData"
                @input="$emit('update:inputData', $event.target.value)"></textarea>
    </div>
    <div class="input__spacer" :class="{ 'input__spacer--error': error }"></div>
  </div>
</template>

<script>
export default {
  name: "RokeInput",
  data() {
    return {
      error: false,
    };
  },
  props: {
    placeholder: {
      default: "",
      type: String,
    },
    inputData: {
      type: String,
      default: "",
    },
    textarea: {
      type: Boolean,
      default: false,
    },
    type: {
      type: String,
      default: "text",
    },
    customId: {
      type: String,
      required: true,
    },
  },
  methods: {
    checkInput(e) {
      this.error = !e.target.validity.valid;
    },
  },
};
</script>

<style lang="scss" scoped>
.input {
  background: transparent;
  width: 100%;
  max-width: 100%;
  border: 0;
  font-size: 1.3rem;
  outline: none;

  input + &__placeholder {
    position: absolute;
    opacity: 1;
  }

  &__placeholder {
    opacity: 0;
    cursor: text;
    bottom: 0.25rem;
    transform-origin: top left;
    transform: translate(0px, 0px);
    transition: all 0.25s ease-in-out;
  }

  &:focus + &__placeholder,
  &:valid + &__placeholder,
  &__placeholder--top {
    transform: translate(-5%, -100%) scale(0.8, 0.8);
    opacity: 1;
  }

  &__wrapper {
    padding: 0.25rem 0.25rem 0.25rem 0.75rem;
    position: relative;
  }

  &__spacer {
    background-color: black;
    width: 100%;
    height: 3px;
    position: relative;
    border-radius: 30px;
    overflow: hidden;

    &--error {
      background-color: #fd7070;
    }
  }
}
</style>
