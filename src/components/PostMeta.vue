<template>
   <div class="post-meta">
      <div class="code">S{{ post.season }}.E{{ post.episode }}</div>
      <div class="date">{{ post.date }}</div>
      <!-- <template v-if="post.timeToRead">
        <strong>{{ post.timeToRead }} min read.</strong>
      </template> -->
    </div>
</template>

<script>
export default {
  props: ['post']
}
</script>

<style lang="scss">
.post-meta {
  font-size: .8em;
  opacity: .8;
}
</style>