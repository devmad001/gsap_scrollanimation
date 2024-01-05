<script>
  export let btnContent
  export let btnClass
</script>

<button class="btn btn--{btnClass}">{btnContent}</button>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";

  .btn {
    border: none;
    border-radius: 3rem;
    color: #fff;
    font-size: $font-xs;
    font-weight: 900;

    &--primary {
      padding: $spacing-xs $spacing-l;
    
      @include respond(tab) {
        margin-right: $spacing-xs;
      }

      &::after {
        content: "v1.3";
        margin-left: .4rem;
      }

      &-1 {
        background-color: $primary-btn-color;

        &::after {
          color: $primary-btn-1-secondary-text-color;
        }
      }

      &-2 {
        background-color: $secondary-btn-color;

        &::after {
          color: $primary-btn-2-secondary-text-color;
        }
      }


    }

    &--secondary {
      background-color: $secondary-btn-color;
      padding: $spacing-xs 2.9rem;
    }

    @include respond(desktop) {
      cursor: pointer;

      &--primary {
        &-1:hover {
          background-color: $primary-btn-color--hover;
        }

        &-2:hover {
          background-color: $secondary-btn-color--hover;
        }
      }

      &--secondary {
        &:hover {
          background-color: $secondary-btn-color--hover;
        }
      }
    }
  }
</style>