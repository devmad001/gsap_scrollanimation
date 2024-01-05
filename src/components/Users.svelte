<script>
  export let usersCount
  export let sidePos

  import { gsap } from "gsap"
  import { onMount } from "svelte"
  import { ScrollTrigger } from "gsap/ScrollTrigger"

  gsap.registerPlugin(ScrollTrigger)

  const animationOrder = [2, 10, 4, 8, 12, 6, 3, 11, 7, 1, 5, 9]

  onMount(() => {
    const usersTimeline = gsap.timeline()

    animationOrder.forEach(user => {
      usersTimeline.to(`.users__img--${user}`, {
        opacity: 1,
        scale: 1,
        duration: .5
      })

    })

    ScrollTrigger.create({
      trigger: ".users",
      animation: usersTimeline,
      start: "-150px top",
      ease: "bounce.inOut",
      scrub: 6
    })

  })
</script>

<div class="users users--{sidePos}">
  {#each usersCount as user}
    <img src={`/assets/users/user-${user}.jpg`} class="users__img users__img--{user}" alt="" />
  {/each}
</div>

<style lang="scss">
  @use "../styles/mixins";

  .users {
    display: none;
    gap: 3rem;
    grid-template-columns: repeat(3, 1fr);
    position: absolute;

    &--left {
      left: 2.5vw;

      img:nth-of-type(2) {
        top: -50%;
      }

      img:nth-of-type(5) {
        top: -50%;
      }
    }

    &--right {
      right: 2.5vw;

      img:nth-of-type(2) {
        top: 50%;
      }

      img:nth-of-type(5) {
        top: 50%;
      }
    }

    &__img {
      border-radius: 50%;
      position: relative;
      transform: scale(0);
      opacity: 0;
      width: 10.5rem;
    }

    @include mixins.respond(desktop) {
      & {
        display: grid;
      }
    }
  }
</style>