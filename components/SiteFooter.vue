<template>
  <footer class="container">
    <div class="row go-all-the-way-to-the-top">
      <div class="col text-center">
        <a href="#">↑ {{ data.backtotopLabel }}</a>
      </div>
    </div>
    <div class="row">
      <div class="col footer text-center">
        <a :href="data.privacyUrl">{{ data.privacyLabel }}</a> - Osudio
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'SiteFooter',
  props: {
    data: {
      required: true,
      type: Object
    }
  }
}
</script>

<style>
.footer {
  padding-top:30px;
  color:grey;
  font-size:12px;
}
.footer a, .footer a:hover {
  color:grey;
  font-size: 12px;
  text-decoration: underline;
}

.go-all-the-way-to-the-top {
  padding-top: 100px;
  padding-bottom: 15px;
}
.go-all-the-way-to-the-top a {
  font-size: 30px;
  font-weight: 400;
  color:#000;
}
.go-all-the-way-to-the-top a span {
  font-size:16px;
  display: block;
}
.go-all-the-way-to-the-top a:hover {
  text-decoration: none;
}
</style>
