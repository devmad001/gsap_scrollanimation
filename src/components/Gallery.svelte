<div class="gallery">
  <img src="/assets/desktop/image-woman-in-videocall.jpg" alt="Woman In Video Call" class="gallery__img gallery__img--1">
  <img src="/assets/desktop/image-women-videochatting.jpg" alt="Women Videochatting" class="gallery__img gallery__img--2">
  <img src="/assets/desktop/image-men-in-meeting.jpg" alt="Men In Meeting" class="gallery__img gallery__img--3">
  <img src="/assets/desktop/image-man-texting.jpg" alt="Man Texting" class="gallery__img gallery__img--4">
</div>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";

  .gallery {
    display: grid;
    gap: $spacing-s;
    grid-template-columns: repeat(2, 1fr);
    justify-items: center;

    &__img {
      border-radius: .8rem;
      width: 100%;

      @include respond(desktop) {
        &--1 {
          clip-path: polygon(0% 0%, 100% 0%, 0% 0%, 0% 0%);
        }

        &--2 {
          clip-path: polygon(0% 0%, 0% 0%, 50% 0%, 50% 0%);
        }

        &--3 {
          clip-path: polygon(0% 0%, 100% 0%, 100% 0%, 50% 0%);
        }

        &--4 {
          clip-path: polygon(0% 0%, 0% 0%, 100% 0%, 100% 0%);
        }
      }

    }

    @include respond(tab) {
      gap: .7rem;
      grid-template-columns: repeat(4, 1fr);
    }
  }
</style>