<template>
  <div class="page-wrapper">
    <h1 class="header">Fun with GPT-3</h1>
    <h4>GPT-3 is a natural language AI model.</h4>
    <h4>It is capable of continuing a piece of writing based on a prompt.</h4>
  <form action="" class="text-form">
      <label class="form-label" for="form-text-area">Enter prompt below.</label>
      <textarea
        class="form-control"
        id="form-text-area"
        rows="3"
      ></textarea>
      <button type="submit" class="btn btn-primary my-1">Submit</button>
  </form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<style scoped>

.text-form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-label {
  margin-top: 3rem;
}
#form-text-area {
  margin-top: 3rem;
  width: 70%;
  height: 40%;
  align-content:
  center;
}

.btn-primary {
  margin-top: 1rem;

}

</style>
