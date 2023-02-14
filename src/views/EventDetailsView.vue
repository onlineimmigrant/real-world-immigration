
<script setup>
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventService.js'

const props = defineProps({
  id: {
    required: true,
  },
})
const event = ref(null)
onMounted(() => {
  EventService.getEvent(props.id)
    .then((response) => {
      event.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <div class="container">
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <div class="post-content" v-html="event.description"></div>
  </div>
</div>
</template>

<style scoped>
/* Container styles */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  text-align: left;
}

/* Blog post styles */
.post {
  margin-bottom: 50px;
}

.post-title {
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: left;
}

.post-meta {
  font-size: 14px;
  color: gray;
  margin-bottom: 20px;
  text-align: left;
}

.post-content {
  font-size: 16px;
  line-height: 1.5;
  text-align: left;
}

/* Heading styles */
h1, h2, h3, h4, h5, h6 {
  font-weight: bold;
  margin-bottom: 20px;
  text-align: left;
}

h1 {
  font-size: 48px;
}

h2 {
  font-size: 42px;
}

h3 {
  font-size: 36px;
}

h4 {
  font-size: 30px;
}

h5 {
  font-size: 24px;
}

h6 {
  font-size: 18px;
}

/* Mobile styles */
@media (max-width: 767px) {
  .container {
    padding: 10px;
  }

  .post-title {
    font-size: 28px;
  }

  .post-content {
    font-size: 14px;
  }

  h1 {
    font-size: 36px;
  }

  h2 {
    font-size: 32px;
  }

  h3 {
    font-size: 28px;
  }

  h4 {
    font-size: 24px;
  }

  h5 {
    font-size: 20px;
  }

  h6 {
    font-size: 16px;
  }
}


</style>