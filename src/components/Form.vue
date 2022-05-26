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

<template>
  <div class="container">
    <div class="sample-input">
      <h1>FormKit Starter Project</h1>
      <FormKit
        type="group"
        v-model="formData"
      >
        <FormKit
          type="text"
          label="Rut"
          name="Rut"
          placeholder="Ej: 11111111-1"
          validation="required"
        />
        <FormKit
          type="select"
          label="Region"
          name="region"
          placeholder="Escoger region"
          :options="['Pizza', 'Ice Cream', 'Burger']"
        />
        <FormKit
          type="select"
          label="Comuna"
          name="comuna"
          placeholder="Escoger comuna"
          :options="['Pizza', 'Ice Cream', 'Burger']"
        />
        <FormKit
          type="file"
          label="Imagen"
          name="imagen"
        />
      </FormKit>

      <h2>Modeled group values</h2>
      <pre class="form-data">{{ formData }}</pre>
    </div>
  </div>
</template>

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