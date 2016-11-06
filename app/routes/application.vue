<template lang="html">
  <div class="">
<nav class="panel">
  <div class="panel-heading">
    <h2>Sign Up For My Web App</h2>
    </div>
    <div class="panel-block">
      <p class="control">
        <input class="input" placeholder="First Name"></input>
      </p>
    </div>
    <div class="panel-block">
      <p class="control">
        <input class="input" placeholder="Last Name"></input>
      </p>
    </div>
    <div class="panel-block">
      <p class="control">
        <input class="input" placeholder="Email Address"></input>
      </p>
    </div>
    <div class="panel-block">
      <p class="control">
        <input class="input" placeholder="Current website url"></input>
      </p>
    </div>
      <div class="panel-block">
        <p class="control">
            <span class="select is-fullwidth">
        <select>
          <option>English</option>
          <option>Spanish</option>
        </select>
            </span>
        </p>
      </div>
      <div class="panel-block">
        <p class="control">
            <textarea class="textarea" placeholder="Your Comment"></textarea>
        </p>
      </div>
      <div class="panel-block">
        <p class="control">
          <input class="input" placeholder="Mobile Number"></input>
        </p>
      </div>
      <div class="panel-block">
        <p class="control">
          <input class="input" placeholder="Home Number"></input>
        </p>
      </div>
      <p class="control">
    <button class="button is-primary is-fullwidth">Submit</button>
    <button class="button is-fullwidth">Cancel</button>
      </p>
      </nav>
  </div>
</template>

<script>
const apiUrl = 'http://json-data.herokuapp.com/forms';

export default {
  data() {
    return {
      formInputs: [],
      formValues: [],
      apiUrl,
    };
  },

  methods: {
    getData () {
      fetch(apiUrl)
        .then((r) => r.json())
        .then((formInputs) => {
          this.formInputs = formInputs;
        });
      },

    submitForm() {},

  },
};
</script>
