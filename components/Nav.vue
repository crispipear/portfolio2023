<template>
  <nav>
    <div>
      <NuxtLink to="/">Su Li</NuxtLink>
    </div>
    <div>
      <NuxtLink to="/">About</NuxtLink>
      <NuxtLink to="/work">Work</NuxtLink>
    </div>
  </nav>
</template>
<style lang="scss">
  nav {
    position: fixed;
    z-index: 10;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: $spacing-s $spacing-xxl;
    font-weight: $fw-m;
    font-size: $fs-s;
    background-color: rgba(var(--background-color), 0.8);
    backdrop-filter: blur(8px);
    > div {
      &:last-of-type {
        a {
          margin-left: $spacing-m;
        }
      }
    }
    @include tablet {
      padding: $spacing-m $spacing-xl;
    }
    @include mobile {
      font-size: $fs-xs;
      padding: $spacing-s $spacing-m;
    }
  }
</style>
<script setup>
  const { client } = usePrismic();
  const { data: intro } = await useAsyncData('intro', () => client.getSingle('intro'));
</script>