<template>
  <article class="post">
    <header class="post-header">
      <div class="post-title">
        <h1>Post Title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>
      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small>
          <i class="el-icon-view"></i>
          42
        </small>
      </div>
      <div class="post-image">
        <img
          src="https://holidaygid.ru/wp-content/uploads/2016/03/berlin3.jpg"
          alt="post image"
        />
      </div>
    </header>
    <main class="post-content">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Obcaecati
        provident expedita cum hic quo, neque facilis nesciunt tempore
        asperiores molestias, illum quaerat voluptatibus dolore dignissimos
        animi ut? Officia, enim magnam?
      </p>
    </main>
    <footer>
      <AppCommentForm />
      <div class="comments" v-if="true">
        <AppComment v-for="comment in 4" :key="comment" :comment="comment" />
      </div>
      <div class="text-center" v-else>Комментарие нет</div>
    </footer>
  </article>
</template>

<script>
import AppComment from "@/components/main/Comment";
import AppCommentForm from "@/components/main/CommentForm";

export default {
  validate({ params }) {
    return Boolean(params.id);
  },
  components: { AppComment, AppCommentForm },
};
</script>

<style lang="scss" scoped>
.post {
  max-width: 600px;
  margin: 0 auto;
}

.post-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.post-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.post-image img {
  width: 100%;
  height: auto;
}

.post-header {
  margin-bottom: 1.5rem;
}

.post-content {
  margin-bottom: 2rem;
}
</style>