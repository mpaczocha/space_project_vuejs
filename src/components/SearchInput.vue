<template>
  <input id="search" name="search" :class="{dark: dark}" :value="value" @input="handleChange"/>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      default: false,
    }
  },
  methods: {
    handleChange(e){
      this.$emit('input', e.target.value);
    },
  }
};
</script>

<style lang="scss" scoped>
input {
  margin-top: 15px;
  display: flex;
  flex-direction: column;
  width: 250px;
  color: white;
  text-align: center;
  font-size: 18px;
  font-weight: 300;
  height: 30px;
  border: 0;
  background: none;
  border-bottom: 1px solid white;
  transition: box-shadow 0.5s ease-out;

  @media (min-width: 1024px) {
    font-weight: 400;
  }
}

input:focus {
  outline: none;
  box-shadow: 0 10px 20px -8px rgba(255, 255, 255, 0.5);
}

.dark {
  color: #1E3D4A;
  border-bottom-color: #1E3D4A;
}

.dark:focus {
  outline: none;
  box-shadow: 0 10px 20px -8px rgba(#1E3D4A, 0.2);
}
</style>

