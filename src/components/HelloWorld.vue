<template>
  <div class="page-wrapper">
    <div class="text-wrapper">
      <h1 class="header">Fun with GPT-3</h1>
      <h4 class="header">GPT-3 is a natural language AI model.</h4>
      <h4 class="header">
        It is capable of continuing a piece of writing based on a prompt.
      </h4>
      <p>Your prompt should make it clear what you want.</p>
      <p>i.e. "Suggest three names for a baby."</p>
    </div>
    <form action="" class="text-form">
      <label class="form-label" for="form-text-area"
        >Enter your prompt here.</label
      >
      <textarea
        class="form-control"
        id="form-text-area"
        rows="12"
        placeholder="Write a song about..."
      ></textarea>
      <div class="slider">
        <label for="slider-range">How creative should the response be, from 0 to 1?</label>
        <input type="range" min="0" max="1" value="0.2" class="slider" id="slider-range">
      </div>
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
  height: 100vh;
  width: 100vw;
}

.slider {
  margin-top: 1rem;
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
  border-radius: 0.3rem;
}


.btn-primary {
  margin-top: 1.5rem;
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
