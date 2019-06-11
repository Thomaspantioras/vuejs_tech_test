<template>
  <div v-if="Object.entries(userDetails).length" class="message">
    <h3>Thank you message is displayed here.</h3>
    <display-details :user-details="userDetails"></display-details>
  </div>
</template>
 
<script>
import DisplayDetails from "./DisplayDetails";

export default {
  components: { DisplayDetails },
  props: {
    userDetails: {
      type: Object,
      required: true
    }
  }
};
</script>
 
<style>
.message > h3 {
  font-weight: bold;
  color: #314246;
  font-size: 1.2em;
}
</style>