<template>
  <div class="page-wrapper">
    <div class="text-wrapper">
      <h1 class="header">Fun with GPT-3</h1>
      <h4 class="header">GPT-3 is a natural language AI model.</h4>
      <h4 class="header">
        It is capable of continuing a piece of writing based on a prompt.
      </h4>
      <p>Your prompt must make it clear what you want.</p>
      <p>i.e. "Suggest three names for a baby."</p>
      <p>Or... "Write a slogan for a pencil business."</p>
    </div>
    <form action="" class="text-form">
      <label class="form-label" for="form-text-area"
        >Enter your prompt below.</label
      >
      <textarea
        class="form-control"
        id="form-text-area"
        rows="12"
        placeholder="Write a song about..."
      ></textarea>
      <button type="submit" class="btn btn-primary my-1">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
};
</script>

<style scoped>

.page-wrapper {
  margin: 0;
  padding: 0;
}
.text-wrapper {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.text-form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-label {
  margin-top: 3rem;
  font-weight: 700;
}
#form-text-area {
  margin-top: 3rem;
  width: 50%;
  height: 40%;
  align-content: center;
  background-color: #ffffff;
  border: #ffffff;
  border-radius: 0.4rem;
}


.btn-primary {
  margin-top: 1rem;
  border-radius: 5rem;
  background-color: transparent;
  height: 1.5rem;
  width: 10rem;
  border-color: #ffffff;
  color: #2c3e50;
  font-weight: 700;
}

.btn-primary:hover {
  background-color: #dafcfd;
}
</style>
