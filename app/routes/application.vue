<template lang="html">
  <div class="">
<div class="section page">
<nav class="panel">
  <div class="panel-heading">
    <h2>Sign Up For My Web App</h2>
    </div>
    <div class="panel-block">
      <label class="control has-icon">
        <input class="input" type="user" placeholder="First Name">
          <span class="fa fa-user"></span>
        </input>
      </label>
    </div>
    <div class="panel-block">
      <p class="control has-icon">
        <input class="input" type="user" placeholder="Last Name">
            <span class="fa fa-user"></span>
        </input>
      </p>
    </div>
    <div class="panel-block">
      <p class="control has-icon">
        <input class="input" type="email" placeholder="Email Address">
            <span class="fa fa-envelope"></span>
        </input>
      </p>
    </div>
    <div class="panel-block">
      <p class="control has-icon">
        <input class="input" type="website" placeholder="Current website url">
            <span class="fa fa-globe"></span>
        </input>
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
        <p class="control has-icon">
          <span class="fa fa-comments"></span>
            <textarea class="textarea input" type="textarea" placeholder="Your Comment">
            </textarea>
        </p>
      </div>
      <div class="panel-block">
        <p class="control has-icon">
          <input class="input" type="mobile" placeholder="Mobile Number">
              <span class="fa fa-mobile"></span>
          </input>
        </p>
      </div>
      <div class="panel-block">
        <p class="control has-icon">
          <input class="input" type="tel" placeholder="Home Number">
              <span class="fa fa-phone"></span>
          </input>
        </p>
      </div>
      <p class="control">
    <button class="button is-primary is-fullwidth">Submit</button>
    <button class="button is-fullwidth">Cancel</button>
      </p>
      </nav>
      </div>
  </div>
</template>

<script>
const apiUrl = 'http://json-data.herokuapp.com/forms';

export default {
  data() {
    return {
      apiUrl,
      formInputs: [],
      formValues: [],
    };
  },

  methods: {
    getData () {
      fetch(apiUrl)
        .then((r) => r.json())
        .then((formInputs) => {
          console.log(formInputs);
          this.formInputs = formInputs;
        });
      },

    submitForm() {},

  },
};
</script>
