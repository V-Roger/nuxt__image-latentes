<template>
  <main class="wrapper">
    <section class="header">
      <logo />
      <h1 class="text-6xl">
        Images latentes
      </h1>
      <h2 class="text-2xl">
        Un podcast de photographie et de photographes argentiques
      </h2>
    </section>
    <hr class="divider">
    <section class="content">
      <ul class="content-platforms">
        <li>
          <a href="https://soundcloud.com/images-latentes" alt="Images latentes sur Soundcloud"><i class="fab fa-soundcloud" /></a>
        </li>
        <!-- <li>
          <a href="" alt=""><i class="fab fa-spotify" /></a>
        </li> -->
        <li>
          <a href="https://www.facebook.com/images.latentes.podcast" alt="Images latentes sur Facebook"><i class="fab fa-facebook" /></a>
        </li>
        <li>
          <a href="https://www.instagram.com/images_latentes/" alt="Images latentes sur Instagram"><i class="fab fa-instagram" /></a>
        </li>
      </ul>
      <iframe
        width="50%"
        height="166"
        scrolling="no"
        frameborder="no"
        allow="autoplay"
        src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/753753574%3Fsecret_token%3Ds-rEAjW&color=%23495057&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"
      />
    </section>
  </main>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style lang="scss" scoped>
  main {
    width: 100%;
    min-height: 100vh;
  }

  .logo {
    margin-bottom: 10vh;
  }

  section {
    position: relative;
    z-index: 1;
    width: 100%;
    height: 90vh;
    display: flex;
    flex-flow: column nowrap;
    align-content: center;
    justify-content: center;
    align-items: center;
    justify-items: center;
  }

  section.header {
    background: #E9ECEF;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
  }

  hr.divider {
    position: relative;
    height: 5vh;
    background: #868E96;
    z-index: -1;
  }

  section.content {
    background: #212529;
    color: white;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;

    .content-platforms {
      list-style-type: none;
      padding: 0;
      margin: 0;
      display: flex;
      flex-flow: row wrap;
      width: 100%;
      justify-content: center;

      & li {
        font-size: 5em;
        padding: 24px;

        & a {
          padding: 24px;
          border: 2px solid transparent;
          border-radius: 3px;

          &:hover,
          &:focus {
            border-top-color: red;
            border-bottom-color: red;
            color: red;
          }
        }
      }
    }
  }
</style>
