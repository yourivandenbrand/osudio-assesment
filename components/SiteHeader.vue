<template>
  <header class="container">
    <div class="row head">
      <div class="col">
        <a :href="data.logoLink">
          <img :src="data.logo" :alt="data.text" />
        </a>
      </div>
      <div class="col text-right">
        <a :href="link">← {{ data.text }}</a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'SiteHeader',
  props: {
    data: {
      required: true,
      type: Object
    }
  },

  computed: {
    link() {
      return this.data.textLink || 'javascript:window.history.back()'
    }
  }
}
</script>

<style>
.head {
  padding-top: 60px;
  padding-bottom: 20px;
}
.head a {
  font-size: 22px;
  font-family: 'Sarala', 'Open Sans', 'Helvetica Neue', Helvetica, sans-serif;
  line-height: 31px;
  color:#000;
  font-weight: 700;
  margin-top: -10px;
  display: inline-block;
}
.head a:hover {
  text-decoration: none;
}

@media screen and (max-width: 992px) {
  .head a {
    font-size: 16px;
    line-height: 110%;
  }
  .head img {
    height: 30px;
  }
}
@media screen and (max-width: 768px) {
  .head {
    padding-top: 20px;
  }
  .head a {
    font-size: 12px;
    line-height: 110%;
  }
}
</style>
