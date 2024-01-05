<script>
  import Button from "./Button.svelte"
  import Counter from "./Counter.svelte"
</script>

<footer class="footer">
  <Counter count="2" />
  <h2 class="footer__headline">Experience more together</h2>
  <p class="footer__description">Stay connected with reliable HD meetings and unlimited one-on-one and group video sessions.</p>
  <Button 
    btnContent="Download"
    btnClass="primary btn--primary-2" />
</footer>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";

  .footer {
    background-image: linear-gradient(rgba($primary-btn-color, .6), rgba($primary-btn-color, .8)),url("/assets/mobile/image-footer.jpg");
    background-size: cover;
    padding: 0rem 2.4rem 7.2rem 2.4rem;
    position: relative;
    text-align: center;

    &__headline {
      color: #fff;
      font-size: $font-m;
      margin-bottom: $spacing-s;
    }

    &__description {
      color: $bg-color;
      font-size: $font-s;
      font-weight: 500;
      line-height: 2.6rem;
      margin-bottom: $spacing-m;
    }

    @include respond(tab) {
      background-image: linear-gradient(rgba($primary-btn-color, .6), rgba($primary-btn-color, .8)),url("/assets/tablet/image-footer.jpg");
      padding: 9.2rem 9.8rem 6.6rem 9.8rem;

      &__headline {
        font-size: $font-l;
        margin: auto;
        margin-bottom: $spacing-m;
        width: 50%;
      }

      &__description {
        font-size: $font-s;
        margin: auto;
        margin-bottom: $spacing-l;
        width: 60%;
      }
    }

    @include respond(desktop) {
      align-items: flex-start;
      background-image: linear-gradient(rgba($primary-btn-color, .6), rgba($primary-btn-color, .8)),url("/assets/desktop/image-footer.jpg");
      display: flex;
      padding: 11.6rem 16.5rem 10.4rem 16.5rem;
      margin-top: 18rem;
      text-align: left;

      &__headline {
        margin: unset;
        margin-right: 5rem;
        width: unset;
      }

      &__description {
        margin: unset;
        margin-right: 9.2rem;
      }
    }
  }
</style>