<template>
   <div class="post-meta">
      <div class="date">{{ post.date }}</div>
      <div class="code">{{ code }}</div>
      <!-- <template v-if="post.timeToRead">
        <strong>{{ post.timeToRead }} min read.</strong>
      </template> -->
    </div>
</template>

<script>
export default {
  // props: ['post', 'short'],
  props: {
    post: Object,
    short: Boolean,
  },
  computed: {
    code() {
      return this.short ?
        `S${this.post.season}.E${this.post.episode}` :
        `Season ${this.post.season}, Episode ${this.post.episode}`;
    }
  }
}
</script>

<style lang="scss">
.post-meta {
  font-size: .8em;
  display: flex;
  opacity: .33;
  .date {
    &::after {
      content: '/';
      margin: 0 1ch;
    }
  }
}
</style>