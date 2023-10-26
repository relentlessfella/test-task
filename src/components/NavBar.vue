<template>
  <div class="header">
    <div class="container">
      <div class="header-right">
        <a class="pageTitle" href="#home">{{ pageTitle }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageTitle: 'Image Gallery'
    }
  }
}
</script>
<style>
.header {
  display: flex;
  height: 70px;
  background-color: #314451;
  align-items: center;
}
</style>
