<template lang="html">
  <div class="">
<nav class="panel">
  <div class="panel-heading">
    <h2>Sign Up For My Web App</h2>
    </div>
    <div class="panel-block">
        <label class="label">First Name</label>
      <p class="control">
          <input class="input" type="text" placeholder="Text input">
      </p>
    </div>
      <div class="panel-block">
        <label class="label">Last Name</label>
        <p class="control has-icon has-icon-right">
            <input class="input is-success" type="text" placeholder="Text input" value="bulma">
            <i class="fa fa-check"></i>
            <span class="help is-success">This username is available</span>
        </p>
      </div>
      <div class="panel-block">
        <label class="label">Email Address</label>
        <p class="control has-icon has-icon-right">
            <input class="input is-danger" type="text" placeholder="Email input" value="hello@">
            <i class="fa fa-warning"></i>
            <span class="help is-danger">This email is invalid</span>
        </p>
      </div>
      <div class="panel-block">
        <label class="label">Subject</label>
        <p class="control">
            <span class="select">
        <select>
          <option>Select dropdown</option>
          <option>With options</option>
        </select>
            </span>
        </p>
      </div>
      <div class="panel-block">
        <label class="label">Message</label>
        <p class="control">
            <textarea class="textarea" placeholder="Textarea"></textarea>
        </p>
      </div>
      <p class="control">
    <label class="checkbox">
      <input type="checkbox">
      Remember me
    </label>
      </p>
      <p class="control">
    <label class="radio">
      <input type="radio" name="question">
      Yes
    </label>
    <label class="radio">
      <input type="radio" name="question">
      No
    </label>
      </p>
      <p class="control">
    <button class="button is-primary is-fullwidth">Submit</button>
    <button class="button is-link is-fullwidth">Cancel</button>
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
