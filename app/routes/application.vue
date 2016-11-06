<template lang="html">
  <div class="">
    <div class="panel">
    <div class="panel-heading">
        <div class="panel-block">
        <form class="" action="index.html" method="post">
          <input type="button" name="name" value="">
        </form>
        <div class="panel-block">
          <button></button>
        </div>
      </div>
    </div>
    </div>
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
      fetch('apiUrl') {
        .then((r) => r.json())
        .then((formInputs) => {
          this.formInputs = formInputs;
        });
      },
    },

    submitForm() {},

  },
};
</script>
