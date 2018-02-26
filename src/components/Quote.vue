<template>
  <div class="quote">
    <slot></slot>
  </div>
</template>

<script>

</script>

<style scoped>
.quote {
  padding: 1rem;

  font-family: Ruluko, cursive;
  font-size: 1.5rem;

  border: 1px solid #000;
  border-radius: 3px;

  cursor: pointer;
}

.quote:hover {
  background: rgb(248, 192, 192);
}
</style>
