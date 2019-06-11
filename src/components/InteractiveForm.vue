<template>
  <form v-if="!hidden" @submit.prevent="onSubmit">
    <fieldset class="form-details">
      <legend>Step {{ step }}</legend>
      <div class="step-wrapper">
        <!-- <section v-if="step == 1" class="step-1 step-wrapper"> -->
        <section v-if="step == 1" class="step-1">
          <div class="fields-1">
            <label for="email" class="visuallyhidden">Email:</label>
            <input
              type="email"
              id="email"
              v-model.lazy.trim="email"
              placeholder="Email address"
              autofocus
              required
            >
          </div>
        </section>
        <section v-if="step == 2" class="step-2">
          <div class="fields-2">
            <div>
              <label for="name" class="visuallyhidden">Name:</label>
              <input type="text" id="name" v-model.lazy.trim="name" placeholder="Name" required>
            </div>
            <div>
              <label for="postcode" class="visuallyhidden">Post Code:</label>
              <input
                type="text"
                id="postcode"
                v-model.lazy.trim="postcode"
                placeholder="Post code"
                required
              >
            </div>
          </div>
        </section>
        <input type="submit" value="Submit">
      </div>
    </fieldset>
  </form>
</template>
 
<script>
/*TODO validation in form*/
export default {
  data() {
    return {
      step: 1,
      totalSteps: 2,
      email: null,
      name: null,
      postcode: null,
      hidden: false
    };
  },
  methods: {
    nextStep() {
      this.step++;
    },
    onSubmit() {
      if (this.step == 1) {
        this.nextStep();
      } else {
        let userDetails = {
          email: this.email,
          name: this.name,
          postcode: this.postcode
        };
        this.$emit('user-details-submitted', userDetails);

        this.hidden = true;
      }
    }
  }
};
</script>
 
<style>
fieldset.form-details {
  border: none;
  padding: 0;
}
[class*='fields-'] {
  grid-column: 1 / 2;
  margin-top: 4px;
}
legend {
  font-weight: bold;
  color: #314246;
  font-size: 1.2em;
}

.visuallyhidden {
  border: 0;
  clip: rect(0 0 0 0);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}

.form-details label {
  margin-top: 1em;
  font-weight: bold;
}

input {
  width: 15em;
  font-size: 1.2em;
  border-radius: 8px;
  margin: 10px;
}

/* input[type='button'] { */
input[type='submit'] {
  grid-column: 2 / 3;
  align-self: start;
  width: 5em;
  background-color: #5d7464e3;
  color: white;
  text-decoration: none;
}

/* input[type='button']:hover { */
input[type='submit']:hover {
  background-color: #485b61;
}

@media (min-width: 600px) {
  .step-wrapper {
    display: grid;
  }
}
</style>