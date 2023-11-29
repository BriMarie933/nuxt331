<template>
  <div>
    <button :style="{ backgroundColor: color }" @click="handleClick">
      Increment by {{ increment }}
    </button>
    <p>{{ `Count: ${count}` }}</p>
  </div>
</template>

<script>
export default {
  props: {
    increment: {
      type: Number,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    handleClick() {
      this.count = this.count + this.increment > 10 ? 0 : this.count + this.increment;
    },
  },
};
</script>

<style>
/* Your component-specific styles here */
</style>
