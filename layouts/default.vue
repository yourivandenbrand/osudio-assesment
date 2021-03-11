<template>
  <div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'layoutDefault'
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  background-color: #fff;
  font-family:'Open Sans', 'Helvetica Neue', Helvetica, sans-serif;
  font-size: 16px;
  line-height: 23px;
  font-weight: 400;
}

.container {
  max-width: 1330px;
}

.innerpadding {
  padding:80px 63px 70px;
}
.innerpadding-alt {
  padding:80px 40px 0px;
}
.innerpadding-alt > p {
  background:gray;
  min-height:200px;
}
.innerpadding-gift {
  padding:40px;
}
.indexpadding {
  padding-left: 63px;
  padding-right: 63px;
}

.nopadb {
  padding-bottom: 0;
}

.posrel {
  position: relative;
}
.posrel img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

h1 {
  font-size: 45px;
  line-height: 45px;
  font-weight:700;
  font-family: 'Sarala', 'Open Sans', 'Helvetica Neue', Helvetica, sans-serif;
  padding-bottom: 15px;
}
h2 {
  font-size: 30px;
  line-height: 30px;
  font-weight:700;
  font-family: 'Sarala', 'Open Sans', 'Helvetica Neue', Helvetica, sans-serif;
  padding-bottom: 15px;
}

ol.numbered-list {
  counter-reset: li;
  list-style-type: none;
  padding-left: 0;
}
ol.numbered-list > li {
  position: relative;
  padding: 5px 0 15px 40px;
}
ol.numbered-list > li:before {
  content: counter(li);
  counter-increment: li;
  height: 25px;
  width: 25px;
  line-height: 25px;
  border-radius: 50%;
  color: #fff;
  background-color: #000;
  text-align: center;
  position: absolute;
  left: 0;
  top: 4px;
}

.button {
  background: black;
  color:white;
  display: block;
  padding: 25px;
  padding-bottom: 20px;
  font-size: 30px;
  line-height: 30px;
  font-weight:700;
  font-family: 'Sarala', 'Open Sans', 'Helvetica Neue', Helvetica, sans-serif;
  border-radius: 20px;
  margin-bottom: 25px;
}
.button span {
  font-size: 18px;
  font-weight: 400;
  display: block;
}
.button:hover {
  color:#fff;
  background: #333;
  text-decoration: none;
}

.img-fluid {
  width: 100%;
  height: auto;
}

@media screen and (max-width: 992px) {
  .posrel img {
    position: inherit;
    top:inherit;
    left:inherit;
    transform: none;
    padding-bottom: 10px;
  }
  .innerpadding {
    padding:40px 20px 30px;
  }
  .innerpadding-alt {
    padding:0px 20px 0px;
  }
  .indexpadding {
    padding-left: 20px;
    padding-right: 20px;
  }
}
@media screen and (max-width: 768px) {
  .innerpadding {
    padding:40px 0;
  }
  .innerpadding-alt {
    padding-left:0;
    padding-right: 0;
  }
  .indexpadding {
    padding-left: 0px;
    padding-right: 0px;
  }
}
</style>
