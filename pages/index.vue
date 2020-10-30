<template>
  <div class="container">
    <section class="c-hero">
      <div class="c-hero__text-wrap">
        <h1 class="c-hero__text-name">Adetomiwa Isiaka</h1>
        <p class="c-hero__text-about">
          I’m a content strategist and writer currently living in Lagos Nigeria,
          and working at gomoney. I curate news for that new news. and working
          at
          <a href="https://gomoney.global/" target="_blank" class="c-link"
            >gomoney</a
          >. I curate news for
          <a
            href="https://thatnewnews.substack.com/"
            target="_blank"
            class="c-link c-link--red"
            >that new news</a
          >. A contributor on Global Voices. A.K.A Isale Èkó mami.
        </p>
      </div>
      <div class="c-hero__image">
        <img src="~/assets/images/tomiwa.jpg" alt="tomiwa's picture" />
      </div>
    </section>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.container {
  width: 80%;
  margin: 0 auto;
}

a,
.c-link {
  text-decoration: none;
  color: $color-green;

  &--red {
    color: $color-red;
  }
}

.c-hero {
  display: flex;
  justify-content: space-between;
  margin-top: 148px;

  &__text {
    &-wrap {
      padding-top: 70px;
      width: 50%;
      z-index: 1;
    }

    &-name {
      font-size: 11.3rem;
      // text-transform: uppercase;
      white-space: nowrap;
      pointer-events: none;
      font-family: 'PlayfairDisplay';
      // font-weight: 500;
    }

    &-about {
      margin-top: 45px;
      max-width: 620px;
      width: 100%;
      font-size: 3rem;
      line-height: 45px;
    }
  }

  &__image {
    width: 525px;
    height: 685px;
    background: #7eb5bd;
    overflow: hidden;

    img {
      transition: 1.2s $easeOutExpo;
      object-fit: contain;

      &:hover {
        transform: scale(1.06);
      }
    }
  }
}
</style>
