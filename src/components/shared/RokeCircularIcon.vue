<template>
  <div :style="`background-color: ${color}`" class="icon">
    <img
      :alt="title + ' Logo'"
      :src="logo"
      class="icon__image"
      height="100"
    />
    <p class="icon__description">{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: "RokeCircularIcon",
  props: {
    color: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    logo: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.icon {
  height: 200px;
  width: 200px;
  background-color: #c1f3de;
  border-radius: 200px;
  margin: 25px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: background-color 250ms ease-in-out, filter 250ms ease-in-out;
  filter: saturate(100%);

  // drop-shadow
  &::after {
    content: "";
    position: absolute;
    height: 200px;
    width: 200px;
    border-radius: 200px;

    z-index: -1;
    box-shadow: 0 5px 15px rgba(124, 124, 124, 0.3);
    opacity: 0;
    -webkit-transition: all 250ms ease-in-out;
    transition: all 250ms ease-in-out;
  }

  &:hover {
    box-sizing: border-box;
    filter: saturate(150%);

    &::after {
      opacity: 1;
    }
  }

  &__image {
  }

  &__description {
    margin-bottom: 0;
    font-weight: bold;
  }
}
</style>
