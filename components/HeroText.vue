<template>
  <div class="container">
    <div :class="['row hero-text innerpadding', {'text-center': !data.image}]">
      <div :class="['col-lg-6', {'offset-lg-3': !data.image}]">
        <h1>{{ data.title }}</h1>
        <h2 v-if="data.subtitle">{{ data.subtitle }}</h2>
        <p v-if="data.body">{{ data.body }}</p>
        <p class="note" v-if="data.note">{{ data.note }}</p>
      </div>
      <div v-if="data.image" class="col-10 offset-1 col-sm-6 offset-sm-3 col-lg-4 offset-lg-1 posrel">
				<img :src="data.image" class="img-fluid" :alt="data.title" />
			</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeroText',
  props: {
    data: {
      required: true,
      type: Object
    }
  }
}
</script>

<style scoped>
.hero-text {
  background: #0098ff;
  color: white;
  margin-bottom: 22px;
  padding-top: 60px;
  padding-bottom: 55px;
}
.note {
  opacity: 0.5;
}
</style>
