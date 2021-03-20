<template>
  <section class="hero">
    <div class="hero__container">
      <div class="hero__section">
        <h2 class="hero__catch-line">Building smarter websites.</h2>
        <p class="hero__sub-line">Wether you're planning a holiday, sharing a shopping list with a pertner or managing multiple work projects.</p>
      </div>
      <div class="hero__section">
        <div class="hero__image"></div>
        <div class="hero__bubble hero__bubble--top-right">I'm a Developer by &lt;3</div>
        <div class="hero__bubble">I'm a Developer by &lt;3</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "roke-hero",
};
</script>

<style lang="scss" scoped>
.hero {
  box-sizing: border-box;
  // background
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

  padding-top: 82px;
  height: 90vh;
  width: 100vw;

  &__container {
    @extend .container;

    display: flex;
    align-items: center;
    height: 100%;
  }

  &__section {
    box-sizing: content-box;
    width: 50%;
    padding: 2rem;
  }

  &__catch-line {
    text-align: left;
    font-size: 5rem;
  }

  &__sub-line {
    font-size: 1.2rem;
    width: 60%;
  }

  &__bubble {
    // appearance
    background: rgba(255, 255, 255, 0.5);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    text-align: center;

    // position
    top: calc(50% + 150px);
    left: calc(55%);
    position: absolute;

    // size
    line-height: 50px;
    height: 50px;
    width: 250px;

    &--top-right {
      // position
      top: calc(50% - 200px);
      left: calc(55% + 300px);
      position: absolute;
    }
  }

  &__image {
    background-color: rgba(255, 255, 255, 0.25);
    background-image: url(../assets/images/serious.jpg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    height: 500px;
    width: 500px;
    margin: 0 auto;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border-radius: 1000px;
    border: 1px solid rgba(255, 255, 255, 0.18);
  }
}
</style>
