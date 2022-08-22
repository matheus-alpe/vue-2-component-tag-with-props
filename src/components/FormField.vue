<template>
  <form class="form" @submit.prevent="emitEvent">
    
    <p>
      <label for="message">{{ value }}</label>
    </p>
    
    <input 
      type="text"
      id="message"
      :value="value"
    />

    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  name: 'FormField',
  props: {
    value: {
      type: String,
      default: 'default'
    }
  },

  methods: {
    emitEvent() {
      console.log('emitting event...')
      this.$emit('show-message')
    }
  }
}
</script>