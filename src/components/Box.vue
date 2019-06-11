<template>
  <div class="box">
    <h3>{{title}}</h3>
    <p>{{content}}</p>
  </div>
</template>
 
<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    }
  }
};
</script>
 
<style>
.box {
  border: 1px solid #485b61;
  background-color: #f3f8f6;
  border-radius: 10px;
  text-align: center;
  padding: 1em;
}

.box h3 {
  font-weight: bold;
  color: #314246;
  font-size: 1.2em;
}
</style>