<template>
  <nav class="BreadcrumbNav">
    <div class="BreadcrumbNav-container">
      <ul>
        <li class="BreadcrumbNav-item"><a href="https://nhsproviders.org">Home</a></li>
        <li class="BreadcrumbNav-item"><a style="outline: 0;" href=""
            @click.self.prevent="changePage('instructions')">Health Inequalities
            Self-Assessment Tool</a></li>
        <li class="BreadcrumbNav-item"><a style="outline: 0;" href="" @click.self.prevent="">{{ page }}</a></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'BreadCrumb',
  props: {
    page: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
