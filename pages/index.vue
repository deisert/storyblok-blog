<template>
  <section class="container">
      <nuxt-link v-for="post in posts" :key="post.id" :to="post.id">
        <article class ="post-preview">
          <div 
          class="post-preview-thumbnail"
          :style="{backgroundImage: post.thumbnailUrl}">

            <div class="post-preview-content">
              <h1>{{post.title}}</h1>
              <p>{{post.previewText}}</p>
            </div>

          </div>
        </article>
      </nuxt-link>
  </section>
</template>



<script>
export default {
  data() {
    return {
      posts: [{
          title: 'A New Beginning', 
          previewText: 'This will be great!',
          thumbnailUrl: 'https://toppng.com/uploads/preview/green-check-mark-11551048866etxqjezdpz.png', 
          id: 'a-new-beginning'
        },
        {
          title: 'The Second Beginning', 
          previewText: 'This will be great, too!',
          thumbnailUrl: 'https://toppng.com/uploads/preview/green-check-mark-11551048866etxqjezdpz.png', 
          id: 'a-second-beginning'
        }
      ]
    }
  }
}
</script>

<style>

</style>
