<template>
  <div id="app">

    <header class="header" v-if="showLogo">
      <div class="header__left">
        <Logo /> 
      </div>
      
      <p class="header__right">        
        <!-- <ToggleTheme /> -->
        <g-link class="link" to="/about">About</g-link>
        <g-link class="link" to="/episodes">Episodes</g-link>
        <!-- <g-link class="link" to="/contact">Contact</g-link> -->
      </p>
    </header>

    <main class="main" :class="{ padded: showLogo }">
      <slot/>
    </main>

    <Author class="post-author" v-if="showLogo" />

    <footer class="footer" v-if="showLogo">

      <span class="footer__copyright">© {{ new Date().getFullYear() }} YBT Media</span>
      <!-- <span class="footer__links">Powered by <a href="//gridsome.org"> Gridsome </a></span> -->
    </footer>

  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import ToggleTheme from '~/components/ToggleTheme.vue'
import Author from '~/components/Author.vue'

export default {
  props: {
    showLogo: { default: true }
  },
  components: {
    Author,
    Logo,
    ToggleTheme
  }
}
</script>

<style lang="scss">
.padded {
  padding: 0 calc(var(--space) / 2);
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: var(--desktop-width);
  margin-left: auto;
  margin-right: auto;
  min-height: var(--header-height);
  padding: 0 calc(var(--space) / 2);
  top: 0;
  z-index: 10;

  &__left,
  &__right {
    display: flex;
    align-items: center;
    margin: 0;
  }

  &__right {
    .link {
      margin-left: 2ch;
      &:first-child {
        margin-left: 0;
      }
    }
  }

  @media screen and (min-width: 1300px) {
    //Make header sticky for large screens
    position: sticky;
    width: 100%;
  }
}

.main {
  margin: 0 auto;
  // padding: 1.5vw 15px 0;
  > h1 {
    margin: 2em 0 1em;
  }
}

.footer {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: calc(var(--space) / 2);
  text-align: center;
  font-size: .8em;

  > span {
    margin: 0 .35em;
  }

  a {
    color: currentColor;
  }
}

.post-author {
  margin-top: calc(var(--space) / 2);
}
</style>
