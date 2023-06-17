<template>
  <div class="card">
    <img :src="imageProject" class="card-img-top" :alt="project.name">
    <div class=" card-body">
      <h5 class="card-title">
        {{ project.name }}
      </h5>
      <p class="card-text">
        {{ project.description }}
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    project: {
      type: Object,
      required: true
    }
  },

  computed: {
    imageProject() {
      return this.project.image;
    }
  }
}
</script>
<style></style>