<template>
  <div class="wrapper">
    <section class="paragraph">
      <paragraph></paragraph>
    </section>
    <section class="storage-process">
      <interactive-form @user-details-submitted="submittedDetails"></interactive-form>
      <thank-message :user-details="userDetails"></thank-message>
    </section>
    <section class="boxes">
      <boxes></boxes>
    </section>
  </div>
</template>

<script>
import Paragraph from './Paragraph';
import InteractiveForm from './InteractiveForm';
import ThankMessage from './ThankMessage';
import Boxes from './Boxes';

export default {
  data() {
    return {
      userDetails: {}
    };
  },
  methods: {
    submittedDetails(userDetails) {
      this.userDetails = userDetails;
    }
  },
  components: {
    Paragraph,
    InteractiveForm,
    ThankMessage,
    Boxes
  }
};
</script>
<style>
.wrapper {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: auto 0.93fr 2fr;
  justify-items: center;
  margin-top: 5%;
  grid-row-gap: 1.5em;
}
.paragraph {
  grid-column: 2 / 6;
}

.storage-process {
  grid-column: 2 / 6;
  margin-top: 2%;
}

.boxes {
  grid-column: 2 / 6;
}
@media (min-width: 600px) {
  .boxes {
    margin-top: 3%;
  }
}
</style>
