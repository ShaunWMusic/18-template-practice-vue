<template lang="html">
  <div class="">
<div class="section page">
<form class="panel">
  <div class="panel-heading">
    <h2>Sign Up For My Web App</h2>
    </div>
    <div class="panel-block">
      <p class="control has-icon" v-for="formInput in formInputs">
      <template v-if="formInput.type === 'select'">
          <span class="select is-fullwidth">
            <select v-model="formValues[formInput.id]">
              <option :value="undefined">{{formInput.label}}</option>
              <option v-for="option in formInput.options">
                {{ option.label }}
              </option>
            </select>
          </span>
      </template>

      <template v-else>
        <template v-if="formInput.type === 'textarea'">
          <textarea class="textarea input"
            type="textarea"
            :placeholder="formInput.label"
            v-model="formValues[formInput.id]"></textarea>
          <i :class="formInput.icon" class="fa" aria-hidden="true"></i>
        </template>
        <template v-else>
          <input class="input" :placeholder="formInput.label" v-model="formValues[formInput.id]">
          <i :class="formInput.icon" class="fa" aria-hidden="true"></i>
        </template>
      </template>



    <!-- <p class="control has-icon" v-for="data in formInputs">
      <input class="input" type="text" :placeholder="data.label">
      <span class="fa" :class="data.icon"></span>
    </p>

      <div class="panel-block">
      <template v-else="ok">
      </template>
      </div>
      <div class="panel-block">
        <label class="control has-icon">
          <span class="fa fa-comments"></span>
            <textarea class="textarea input" type="textarea" :placeholder="formInputs[5].label">
            </textarea>
        </label>
      </div>
      <div class="panel-block">
        <label class="control has-icon">
          <input class="input" type="mobile" placeholder="Mobile Number">
              <span class="fa fa-mobile"></span>
          </input>
        </label>
      </div>
      <div class="panel-block">
        <label class="control has-icon">
          <input class="input" type="tel" placeholder="Home Number">
              <span class="fa fa-phone"></span>
          </input>
        </label>
      </div> -->
      </p>
    </div>
      <div class="panel-block">
    <button class="button is-primary is-fullwidth">Submit</button>
    <button class="button is-fullwidth">Cancel</button>
  </div>
    </form>
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
      formValues: {},
    };
  },

  mounted() {
    this.getData();
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
