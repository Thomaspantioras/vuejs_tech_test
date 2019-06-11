<template>
  <div class="boxes-wrapper">
    <box v-for="(box, index) in boxes" :key="index" :title="box.title" :content="box.content"></box>
  </div>
</template>
 
<script>
import Box from './Box';

export default {
  components: { Box },
  data() {
    return {
      boxes: [
        {
          title: 'Title 1',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        },
        {
          title: 'Title 2',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        },
        {
          title: 'Title 3',
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        }
      ]
    };
  }
};
</script>
 
<style>
.boxes-wrapper {
  display: grid;
  grid-gap: 10% 15%;
}

@media (min-width: 600px) {
  .boxes-wrapper {
    grid-template-rows: repeat(2, 1fr);
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 15%;
    justify-content: space-around;
  }
  .boxes-wrapper div:last-child {
    grid-column: 1 / 3;
    justify-self: center;
    margin: 0 29%;
  }
}

@media (min-width: 900px) {
  .boxes-wrapper {
    grid-template-columns: repeat(3, 1fr);
  }

  .boxes-wrapper div:last-child {
    grid-column: 3 / 4;
    margin: 0%;
  }
}
</style>