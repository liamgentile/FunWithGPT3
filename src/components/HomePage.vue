<template>
  <div class="page-wrapper">
    <div class="instructions-wrapper">
      <h1 class="header">Fun with GPT-3</h1>
      <h4 class="header">GPT-3 is a natural language AI model.</h4>
      <p class="description">
        It is capable of continuing a piece of writing based on a prompt.
      </p>
      <p>Your prompt should make it clear what you want.</p>
      <p>For example, "Suggest three names for a baby."</p>
    </div>
    <form class="form" v-on:submit.prevent="submit">
      <label class="form-label" for="form-text-area"
        >Enter your prompt here.</label
      >
      <textarea
        class="form-control"
        v-model="input_prompt"
        id="form-text-area"
        rows="12"
        placeholder="Write a song about..."
      ></textarea>
      <div class="slider">
        <label class="slider-label" for="slider-range"
          >How creative should the response be? Drag to the right for more
          creativity.</label
        >
        <input
          type="range"
          min="0"
          max="1"
          step="0.1"
          class="slider-bar"
          v-model="creativity"
          id="slider-range"
        />
      </div>
      <button type="submit" class="btn btn-primary my-1">Submit</button>
    </form>
    <div
      class="response-wrapper"
      v-bind:key="response"
      v-for="response in responses.reverse()"
    >
      <p class="api-response" v-html="response.prompt"></p>
      <p class="api-response" v-html="response.response"></p>
      <p class="api-response" v-html="response.time"></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  data() {
    return {
      input_prompt: "",
      creativity: 0,
      responses: [],
    };
  },
  methods: {
    async submit() {
      fetch("https://api.openai.com/v1/engines/text-curie-001/completions", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          Authorization: `Bearer ${process.env.VUE_APP_OPEN_API_KEY}`,
        },
        body: JSON.stringify({
          prompt: this.input_prompt,
          temperature: this.temperature,
        }),
      })
        .then((res) => res.json())
        .then((response) => {
          console.log(response);

          this.responses.push({
            prompt: "Prompt: ".bold() + this.input_prompt,
            response: "Response: ".bold() + response.choices[0].text,
            time: new Date(),
          });
        })
        .catch((error) => {
          error.response.status;
        });
    },
  },
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
.instructions-wrapper {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-label {
  margin-top: 3rem;
  font-weight: 700;
}
#form-text-area {
  margin-top: 1.5rem;
  width: 55%;
  max-width: 80%;
  height: 40%;
  align-content: center;
  background: #faf9f6;
  border: none;
  outline: none;
  border-radius: 0.3rem;
  box-shadow: 2.5px 3px #2c3e50;
}

.btn-primary {
  margin-top: 2rem;
  margin-bottom: 3rem;
  border-radius: 5rem;
  background-color: transparent;
  height: 2rem;
  width: 10rem;
  border-color: #ffffff;
  color: #2c3e50;
  font-weight: 700;
  font-size: 1rem;
}

.btn-primary:hover {
  background-color: #dafcfd;
}

.slider-bar {
  accent-color: #cab8f8;
}

.slider-bar:hover {
  accent-color: #dafcfd;
}

.slider-label {
  font-weight: 700;
}

.slider {
  max-width: 80%;
}
.description {
  border-bottom: 2px solid #2c3e50;
  padding-bottom: 1.5rem;
  max-width: 95%;
}

.response-wrapper {
  justify-content: center;
  padding-bottom: 3rem;
  flex-direction: column;
  display: flex;
}

.api-response {
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
}
</style>
