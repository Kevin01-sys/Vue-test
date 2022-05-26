<template>
  <div class="container">
    <div class="sample-input">
      <h1>FormKit Starter Project</h1>
      <FormKit
        type="group"
        v-model="formData"
      >
        <FormKit
          name="hello_world"
          label="Hello World"
          placeholder="Enter something here..."
          validation="required"
          validation-behavior="live"
          help="Read the docs for more info on using FormKit"
        />
        <FormKit
          name="opinion"
          label="Opinion"
          help="How excited are you about FormKit?"
          type="radio"
          value="A lot"
          :options="['A little', 'A lot']"
        />
        <div class="side-by-side">
          <FormKit
            name="recommendation"
            label="Recommendation"
            v-model="recommendation"
            help="How likely are you to recommend FormKit to a friend?"
            type="range"
            min="0"
            max="10"
          />
          <pre class="range-output">{{ recommendation }} </pre>
        </div>
      </FormKit>

      <h2>Modeled group values</h2>
      <pre class="form-data">{{ formData }}</pre>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const recommendation = ref('10')
    const formData = ref({})

    return {
      recommendation,
      formData
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  margin: auto;
  display: flex;
  justify-content: center;
}

.side-by-side {
  display: flex;
  align-items: flex-start;
}

pre.range-output {
  background: #eee;
  border-radius: 0.5em;
  text-align: center;
  margin-left: 1em;
  margin-top: 1.5em;
  font-weight: bold;
  padding: 0.5em;
  line-height: 1;
  width: 1.5em;
}

pre.form-data {
  box-sizing: border-box;
  background: #eee;
  border: 1px solid #ccc;
  width: 100%;
  padding: 1em;
  border-radius: 0.5em;
}
</style>
