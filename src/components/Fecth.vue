<template>
  <div>
    <button @click="get_data">{{ name }}</button>
    <ul>
      <li v-for="item in data">
        {{ item }}
      </li>
    </ul>
    {{msg}}
  </div>
</template>

<script setup> // Single file component can contain only one <script setup> element
defineProps({ // variables that are brought in from outside the component, before using it
  msg: { 
    type: String,
    required: true
  }
})
</script>

<script>
export default {
  data() { // component properties
    return {
      data: {},
      name: 'variables state',
      test: "testing"
    }
  },
  beforeMount(){
    this.getName();
  },
  methods: { // component methods
    async getName(){
      const res = await fetch('https://api.agify.io/?name=michael');
      const data = await res.json();
      this.data = data;
    },
    get_data(){
        const url = "https://api.agify.io/?name=michael"
        fetch(url)
        .then(response => response.json())
        .then((json_data) => {
            console.log(json_data)
            this.data = json_data
            //console.log(this.data)
        })
        .catch((error) => {
            console.log(error)
        })
        //console.log(event.target.id)
    }
  }
};
</script>
