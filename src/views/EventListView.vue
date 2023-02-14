<script setup>
import { ref, onMounted } from 'vue'
import EventCard from '@/components/EventCard.vue'
import EventService from '@/services/EventService.js'
const events = ref(null)
onMounted(() => {
  EventService.getEvents()
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<script>
export default {
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        left: 0,
        behavior: "smooth"
      });
    }
  }
};
</script>


<template>
  <div class="row">
    <div class="col">
      <h2>Top Article</h2>
      <p>Column 1</p>
    </div>

    <div class="col">
      <h1>Nutrition Blog</h1>
      <p>News, useful links, etc.</p>
      <div class="events">
        <EventCard v-for="event in events" :key="event.id" :event="event" />
      </div>
    </div>

    <div class="col">
      <h2>Sections</h2>
      <p>Column 1</p>
    </div>
  </div>

  <nav class="mobile-nav">
    <a href="#">
      <img class="mobile-nav-size"
        src="https://res.cloudinary.com/dzagcqrbp/image/upload/v1676188755/onlineimmigrant/xoxkhhdjm0wljdqib3yq.svg"
        alt="Image 1">
    </a>
    <a href="#">
      <img class="mobile-nav-size"
        src="https://res.cloudinary.com/dzagcqrbp/image/upload/v1676188755/onlineimmigrant/bt2ybs4wqq9yjw887qry.svg"
        alt="Image 2">
    </a>
    <a href="#">
      
      <img class="mobile-nav-size"
        src="https://res.cloudinary.com/dzagcqrbp/image/upload/v1676188755/onlineimmigrant/buah21pkx1asqb9vhlad.svg"
        alt="Image 3">
    
    </a>
    <a @click="scrollToTop" href="#">
      
      <img class="mobile-nav-size"
        src="https://res.cloudinary.com/dzagcqrbp/image/upload/v1676191558/onlineimmigrant/hzv6dfsmmxin5itkmhmr.svg"
        alt="Image 4">
     
    </a>
  </nav>
</template>


<style>

</style>