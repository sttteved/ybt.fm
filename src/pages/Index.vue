<template>
  <Layout :show-logo="false">
    <div class="home">
      <div class="home__about">
        <g-image alt="Y'all Boys" src="~/assets/images/author.webp" width="680" height="680" quality="100" />
        <h1>{{ $static.metaData.siteName }}</h1>
        <h6>{{ $static.metaData.siteTagline }}</h6>
      </div>
      <nav class="home__nav">
        <g-link class="link" to="/about">About</g-link>
        <g-link class="link" to="/episodes">Episodes</g-link>
        <!-- <g-link class="link" to="/contact">Contact</g-link> -->
        <h6>Listen now:</h6>
        <a target="_blank" class="link spotify" href="//open.spotify.com/show/5xzMcpzL8T5g7zGqNMoQcB?si=zEyr_F4oQs6El1av3kT8iA&fbclid=IwAR3i67W65XU4Fl8HpIduxKlhzVsPwT2XP3a6vbxKc2WYUUF-SCXfPzHRWIc">Spotify</a>
        <a target="_blank" class="link apple" href="//podcasts.apple.com/us/podcast/yall-boys-talkin/id1452781895?mt=2">Apple Podcasts</a>
        <a target="_blank" class="link google" href="//play.google.com/music/listen#/ps/Icqw2qixlfgyrebhomlxrhen7k4">Google Podcasts</a>
      </nav>
    </div>
  </Layout>
</template>

<static-query>
query {
  metaData {
    siteName
		siteTagline
  }
}
</static-query>

<script>
import Author from '~/components/Author.vue'
import PostCard from '~/components/PostCard.vue'

export default {
  components: {
    Author,
    PostCard
  },
  metaInfo: {
    title: 'Home'
  }
}
</script>

<style lang="scss">
.home {
  display: grid;
  margin: 0 auto;
  min-height: 100vh;
  max-width: calc(var(--desktop-width) + var(--grid-gap));
  align-items: center;
  justify-content: center;
  grid-template-columns: repeat(var(--grid-columns), var(--grid-column-width));
  grid-column-gap: var(--grid-gap);
  &__about {
    grid-column-start: span 7;
    img {
      display: block;
      border-radius: var(--radius);
    }
    h1 {
      margin: .5em 0 .25em;
    }
    h6 {
      margin: 0;
    }
  }
  &__nav {
    background: var(--bg-content-color);
    height: 100%;
    grid-column-start: 9;
    grid-column-end: 13;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    padding: 0 calc(var(--grid-gap) * 2);
    .link {
      font-size: 2em;
      font-family: 'Playfair Display', serif;
      &::after {
        display: none !important;
      }
      &:first-child {
        margin-top: -3em;
      }
      @media screen and (max-width: 1200px) {
        font-size: 1.5em;
      }
    }
    h6 {
      margin: 4em 0 0;
    }
  }
  h6 {
    font-size: 0.9em;
    font-weight: bold;
  }
  .spotify {
    color: #1ED760;
  }
  .apple {
    color: #9933CC;
  }
  .google {
    color: #4285F4;
  }
  @media screen and (max-width: 960px) {
    display: flex;
    flex-flow: column nowrap;
    &__about {
      min-height: 80vh;
      padding: calc(var(--grid-gap) * 2);
      display: flex;
      flex-flow: column nowrap;
      justify-content: center;
    }
    &__nav {
      min-height: 80vh;
      width: 100%;
      justify-content: flex-start;
      padding-top: calc(var(--grid-gap) * 2);
      .link:first-child {
        margin-top: 0;
      }
    }
  }
}
</style>