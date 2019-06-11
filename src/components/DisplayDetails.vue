<template>
  <ul>
    <li>
      <span>Name:</span>
      {{ this.userDetails.name }}
    </li>
    <li>
      <span>Email:</span>
      {{ this.userDetails.email }}
    </li>
    <li>
      <span>Post code:</span>
      {{ this.userDetails.postcode }}
    </li>
  </ul>
  <!-- </div> -->
</template>
 
<script>
export default {
  props: {
    userDetails: {
      type: Object,
      required: true
    }
  }
};
</script>
 
<style>
ul {
  list-style-type: none;
  padding-inline-start: 0;
}
span {
  font-weight: bold;
  color: #314246;
  font-size: 1em;
}
</style>