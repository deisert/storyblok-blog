<template>
  <section id="posts" class="container">
      <PostPreview 
        v-for="post in posts" 
        :key="post.id" 
        :title="post.title"  
        :excerpt="post.previewText"
        :thumbnailImage="post.thumbnailUrl"
        :id="post.id" 
      />
  </section>
</template>

<script>
import PostPreview from "@/components/Blog/PostPreview"

export default {
  components: { 
    PostPreview
  },
  
  asyncData(context) {
    return context.app.$storyapi
      .get("cdn/stories", { 
        version: 'draft', // means development Mode
        starts_with: 'blog/'
      })
    .then(res => { 
        return {
          posts: res.data.stories.map(bp => {
          return {
            id: bp.slug, 
            title: bp.content.title, 
            previewText: bp.content.summary, 
            thumbnailUrl: bp.content.thumbnail
          }
        })
        };
    });
  }
}
//   data() {
//     return {
//       posts: [{
//           title: 'A New Beginning', 
//           previewText: 'This will be great!',
//           thumbnailUrl: 'https://www.advantageaustria.org/GenticsImageStore/auto/300/prop/zentral/news/aktuell/Storyblok_Logo.jpg', 
//           id: 'a-new-beginning'
//         },
//         {
//           title: 'The Second Beginning', 
//           previewText: 'This will be great, too!',
//           thumbnailUrl: 'https://www.advantageaustria.org/GenticsImageStore/auto/300/prop/zentral/news/aktuell/Storyblok_Logo.jpg', 
//           id: 'a-second-beginning'
//         }
//       ]
//     }
//   }
// }
</script>

<style scoped>
#posts {
  padding-top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
@media (min-width: 35rem) {
  #posts {
    flex-direction: row;
  }
}
</style>