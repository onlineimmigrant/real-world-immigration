<script setup>
defineProps({
  event: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <RouterLink class="event-link" :to="{ name: 'event-details', params: { id: event.id } }">

    <div class="card">

      <img class="card-image" :src="event.image" :alt="event.alt" />
      <div class="card-header">{{ event.section }}</div>
      <h2 class="card-title">{{ event.title }}</h2>
      <span class="card-text" v-html="event.description"></span>


      <span class="card-footer">@{{ event.time }} | {{ event.date }}</span>

    </div>

  </RouterLink>
</template>

<style scoped>
.hr {
  border: 0;
  border-top: 2px dotted grey;
}

.body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  color: #333;
  background-color: #fafafa;
  padding: 20px;
}


</style>
