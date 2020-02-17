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
    <masonry
      :cols="{default: 5, 1000: 3, 700: 2, 400: 1}"
      :gutter="'8px'"
      class="gallery"
    >
      <img v-for="photo in photos" :key="photo" :src="photo.pathLong">
    </masonry>
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
        width="90%"
        height="166"
        scrolling="no"
        frameborder="no"
        allow="autoplay"
        src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/762254818&color=%23646c6c&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"
      />
      <blockquote cite="http://daviddarle.com/">
        <p>
          Voilà c'est vraiment ça la photo hein, là on est en plein dedans, c'est vraiment écrire avec la lumière.
        </p>
        <footer>David Darle, <cite>Images Latentes épisode 00</cite></footer>
      </blockquote>
    </section>
  </main>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data: () => ({
    photos: []
  }),
  mounted () {
    this.importAll(require.context('../assets/photos', true, /\.jpg$/))
  },

  methods: {
    importAll (r) {
      r.keys().forEach(key => (this.photos.push({ pathLong: r(key), pathShort: key })))
    }
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
    min-height: 90vh;
    display: flex;
    flex-flow: column nowrap;
    align-content: center;
    justify-content: center;
    align-items: center;
    justify-items: center;

    @media all and (max-width: 1000px) {
      padding: 24px;
    }
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

  .gallery {
    position: relative;
    padding-left: 16px;
    padding-right: 24px;
    left: 8px;
    padding-top: 24px;
    width: 100%;
    background: #212529;
  }

  section.content {
    background: #212529;
    color: white;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    padding-bottom: 80px;
    justify-content: space-evenly;

    h2 {
      font-size: 2em;
    }

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

        @media all and (max-width: 800px) {
          font-size: 3em;
        }

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
    & blockquote {
      position: relative;
      top: 5em;
      max-width: 80vw;

      &:before {
        content: '“';
        display: block;
        position: absolute;
        left: -1em;
        top: -1em;
        font-size: 3em;
      }

      &:after {
        content: '”';
        display: block;
        position: absolute;
        right: -1em;
        bottom: -1em;
        font-size: 3em;
      }

      p {
        font-size: 1.6em;
      }

      footer {
        font-size: 1em;
        padding: 8px 16px;
        margin-left: 16px;
        margin-top: 8px;
        border-left: 4px solid white;
      }

      @media all and (max-width: 800px) {
        max-width: calc(80vw - 4em);
        margin-bottom: 5em;

        &:before {
          left: 0;
        }

        &:after {
          right: 0;
        }
      }
    }
  }
</style>
