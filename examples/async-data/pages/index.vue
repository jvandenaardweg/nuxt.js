
<template>
  <div class="container">
    <h1>User Agent</h1>
    <p>{{ userAgent }}</p>
    <p><nuxt-link to="/posts">Blog</nuxt-link></p>
  </div>
</template>

<script>
export default {
  asyncData ({ req }, callback) {
    setTimeout(function () {
      // callback(err, data)
      callback(null, {
        userAgent: (req ? req.headers['user-agent'] : navigator.userAgent)
      })
    }, 100)
  }
}
</script>

<style scoped>
.container {
  width: 70%;
  margin: auto;
  text-align: center;
  padding-top: 100px;
}
p {
  font-size: 20px;
}
a {
  color: #41B883;
}
</style>
