<template>
  <section class="hero">
    <div class="hero__container">
      <div class="hero__section">
        <h2 class="hero__catch-line">Building smarter websites.</h2>
        <p class="hero__sub-line">Wether you're planning a holiday, sharing a shopping list with a pertner or managing
          multiple work projects.</p>
      </div>
      <div class="hero__section--image">
        <div class="hero__image">
          <div class="hero__bubble hero__bubble--top-right">I'm a Developer by &lt;3</div>
          <div class="hero__bubble">I'm a Developer by &lt;3</div>
        </div>

      </div>
    </div>
    <svg class="hero__arch container__arch" fill="none" preserveAspectRatio="none" viewBox="0 0 1680 40"
         xmlns="http://www.w3.org/2000/svg">
      <path d="M0 40h1680V30S1340 0 840 0 0 30 0 30z" fill="#fff"></path>
    </svg>
  </section>
</template>

<script>
export default {
  name: "roke-hero",
};
</script>

<style lang="scss" scoped>
.hero {
  position: relative;
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
  height: 98vh;
  width: 100vw;
  min-height: 500px;

  @include md {
    min-height: 600px;
  }

  @include lg {
    min-height: 700px;
  }

  &__container {
    @extend .container;

    padding-top: 0;
    display: flex;
    align-items: center;
    height: 100%;
    flex-wrap: nowrap;
  }

  &__section {
    box-sizing: content-box;
    padding: 2rem;
    width: 100%;
    z-index: 20;

    @include sm {
      width: 70%;
    }
    @include md {
      width: 60%;
    }
    @include lg {
      width: 50%;
    }

    &--image {
      position: absolute;
      right: 25px;
      z-index: 0;
      margin-top: 50px;
      transition: all 250ms ease-in-out;

      @include md {
        margin-top: 0;

        z-index: 200;
      }
    }
  }

  &__catch-line {
    text-align: left;
    line-height: 1em;
    margin-bottom: 0.2em;
    font-size: 3rem;

    @include lg {
      font-size: 4rem;
    }

    @include xl {
      font-size: 7rem;
    }
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
    bottom: 10%;
    left: 0;
    position: absolute;

    // size
    line-height: 50px;
    height: 50px;
    width: 250px;

    &--top-right {
      // position
      top: 10%;
      left: unset;
      right: 0;
      position: absolute;
    }
    display: none;

    @include md {
      display: unset;
    }
  }

  &__image {
    background-color: rgba(255, 255, 255, 0.25);
    background-image: url(../assets/images/serious.jpg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    margin: 0 auto;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border-radius: 1000px;
    border: 1px solid rgba(255, 255, 255, 0.18);

    height: 200px;
    width: 200px;

    opacity: 0.5;

    @include sm {
      opacity: 1;
      height: 250px;
      width: 250px;
    }
    @include md {
      height: 300px;
      width: 300px;
    }
    @include lg {
      height: 400px;
      width: 400px;
    }

    @include xl {
      height: 500px;
      width: 500px;
    }
  }

  &__arch {
    position: absolute;
    bottom: 0;
    z-index: 1;
    width: 100%;
  }
}
</style>
