<template>
  <section class="tendency">
      {{ tendency }}
  </section>
</template>

<script>
export default {
  props: ["tendency"],
};
</script>

<style lang="scss" scoped>
.tendency {
  display: flex;
  position: relative;
  clear: both;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: flex-end;
  max-width: 800px;
  padding: 30px;
  margin: 0 auto;
  font-size: 25px;
  font-weight: 600;
  background-color: var(--dark);
  color: var(--lite);
  padding: 32px;
  border-radius: 30px 30px 0 30px;
}
</style>
