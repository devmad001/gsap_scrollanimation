<script>
  import Gallery from "./Gallery.svelte"
  import Counter from "./Counter.svelte"
</script>

<section class="feature-description">
  <Counter count="1" />
  <Gallery />
  <div class="feature-description__text">
    <p class="feature-description__subheadline">Built For Modern Use</p>
    <h2 class="feature-description__headline">Smarter meetings, all in one place</h2>
    <p class="feature-description__description">Send messages, share files, show your screen, and record your meetings — all in one workspace. Control who can join with invite-only team access, data encryption, and data export.</p>
  </div>
</section>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";

  .feature-description {
    padding: 0 2.4rem;
    padding-bottom: 15rem;
    position: relative;

    &__text {
      margin: $spacing-xxl 0;
      text-align: center;
    }

    &__subheadline {
      color: $primary-btn-color;
      font-size: $font-xs;
      letter-spacing: .4rem;
      margin-bottom: $spacing-s;
      text-transform: uppercase;
    }

    &__headline {
      font-size: $font-m;
      line-height: 3.6rem;
      margin-bottom: $spacing-m;
    }

    &__description {
      color: $secondary-text-color;
      font-size: $font-xs;
      font-weight: 500;
      line-height: 2.6rem;
    }

    @include respond(tab) {
      padding: 0 9.7rem;

      &__text {
        margin-top: $spacing-xl;
      }
    }

    @include respond(desktop) {
      padding: 0 15.6rem;
      padding-top: 31.4rem;

      &__description {
        margin: auto;
        width: 38%;
      }
    }
  }
</style>
