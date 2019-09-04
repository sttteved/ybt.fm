<template>
  <Layout>
    <!-- Author intro -->
    <!-- <Author :show-title="true" /> -->

    <!-- List posts -->
    <h1 class="text-center">Episodes</h1>
    <div class="posts">
      <PostCard v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node" />
    </div>

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
        date (format: "MMM DD")
        timeToRead
        # description
        season
        episode
        # coverImage (width: 770, height: 380, blur: 10)
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

<script>
import Author from '~/components/Author.vue'
import PostCard from '~/components/PostCard.vue'

export default {
  components: {
    Author,
    PostCard
  },
  metaInfo: {
    title: 'Episodes'
  }
}
</script>
