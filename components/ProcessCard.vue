<template>
  <article class="process-card">
    <div>
      <h3 class="process-card-title">
        {{ title }}
      </h3>
      <div class="process-card-des">
        {{ desc }}
      </div>
    </div>
  </article>
</template>

<script setup>
const props = defineProps({
	title: {
		type: String,
		required: true
	},
	desc: {
		type: String,
		required: true
	}
})
</script>

<style>
.process-card {
  color: #fff;
  margin-bottom: 1rem;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.process-card div {
  text-align: center;
}

.process-card-title {
  font-weight: bold;
  font-size: 1.6rem;
  color: #f33c7a;
}

.process-card-des {
  font-size: 1.2rem;
}
</style>