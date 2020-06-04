<template>
  <div>
  <h1>{{ event.title }}</h1>
  <p>{{event.description}}</p>
  <p>Location: {{event.location}}</p>
  <p>Organiser: {{event.organizer}}</p>
  </div>
</template>
<script>
import EventService from '@/services/EventService.js';
export default {
  props: ['id'],
  data() {
    return {
      event: {}
    }
  },
  created() {
    EventService.getEvent(this.id)
    .then(response => {
      this.event = response.data
    })
    .catch(error => {
      console.log(error)
    })

  }
}
</script>


