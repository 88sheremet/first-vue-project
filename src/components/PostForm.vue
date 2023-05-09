<template>
  <div>
    <form @submit.prevent>
      <h2>Create post</h2>
      <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Name"
      />
      <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Description"
      />
      <button class="button" @click="createPost">Create</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.input {
  width: 80%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.button {
  width: 200px;
  background-color: black;
  color: teal;
  height: 40px;
}
</style>
