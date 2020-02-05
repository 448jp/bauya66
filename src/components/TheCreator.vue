<template>
  <li class="creator">
    <p class="creator_name">
      {{ name }}
    </p>
    <p class="creator_age">
      {{ age }}
    </p>
    <p class="creator_job">
      {{ job }}
    </p>
  </li>
</template>

<script>
export default {
  props: {
    name: String,
    age: Number,
    job: String
  }
};
</script>

<style lang="scss" scoped>
.creator {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 200px;
  height: 240px;
  margin-right: 20px;
  border: 1px solid gray;
  border-radius: 8px;
  background-color: cornsilk;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.4);

  &_name {
    font-size: 18px;
    font-weight: bold;
  }

  &_job {
    font-size: 12px;
  }

  &_age {
    color: green;
  }
}
</style>
