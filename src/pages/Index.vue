<template>
  <Layout :show-logo="false">
    <!-- Author intro -->
    <!-- <Author :show-title="true" /> -->

    <!-- List posts -->
    <!-- <div class="posts">
      <PostCard v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node"/>
    </div> -->

    <g-image alt="Author image" src="~/assets/images/author.webp" width="580" height="580" />
    <h2>{{ $static.metaData.siteName }}</h2>
    <p><strong>{{ $static.metaData.siteTagline }}</strong></p>

  </Layout>
</template>

<page-query>
{
  posts: allPost(filter: { published: { eq: true }}) {
    edges {
      node {
        id
        title
        path
        tags {
          id
          title
          path
        }
        date (format: "MMMM D, YYYY")
        timeToRead
        description
        season
        episode
        coverImage (width: 770, height: 380, blur: 10)
        ...on Post {
            id
            title
            path
        }
      }
    }
  }
}
</page-query>

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
h2 {
  margin-top: .33em;
  margin-bottom: .33em;
}
</style>