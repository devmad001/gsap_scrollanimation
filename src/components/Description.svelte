<script>
  import Button from "./Button.svelte"
</script>

<header class="header">
  <h1 class="header__headline">Group Chat for Everyone</h1>
  <p class="header__subheadline">Meet makes it easy to connect with others face-to-face virtually and collaborate across any device.</p>
  <div class="header__ctas">
    <Button 
      btnColor="#4D96A9" 
      hoverColor="#8FE3F9"
      btnContent="Download"
      btnClass="primary btn--primary-1" />
    <Button 
      btnColor="#855FB1" 
      hoverColor="#D9B8FF"
      btnContent="What is it?"
      btnClass="secondary" />
  </div>
</header>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";

  .header {
    &__headline {
      color: $primary-text-color;
      font-size: $font-l;
      margin: auto;
      margin-bottom: $spacing-s;
      width: 85%;
    }

    &__subheadline {
      color: $secondary-text-color;
      font-size: $font-xs;
      line-height: 2.6rem;
      margin: auto;
      margin-bottom: $spacing-m;
    }

    &__ctas {
      align-items: center;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      height: 12rem;
    }

    @include respond(tab) {
      &__headline {
        font-size: $font-xl;
      }

      &__ctas {
        flex-direction: row;
        height: unset;
        justify-content: center;
      }
    }

    @include respond(desktop) {
      & {
        flex-direction: column;
        margin: auto;
        @include flexCenter;
      }

      &__headline {
        width: 45%;
      }

      &__subheadline {
        width: 70%;
      }
    }
  }
</style>