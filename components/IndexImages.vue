<script setup>
  const props = defineProps(['hidden'])
</script>
<template>
  <div id="hero_img_b" :class="hidden ? 'hero-img' :'hero-img hero-img-show-b'">
    <img src="@/assets/images/hero.png" id="hero_img_bLeft" />
    <img src="@/assets/images/hero.png" id="hero_img_bRight" />
  </div>
  <div id="hero_img_t" :class="hidden ? 'hero-img' :'hero-img hero-img-show-t'">
    <img src="@/assets/images/hero.png" id="hero_img_tLeft" />
    <img src="@/assets/images/hero.png" id="hero_img_tRight" />
  </div>
</template>
<style lang="scss">
  .hero-img{
    position: fixed;
    width: 100vw;
    left: 0;
    z-index: 100;
    pointer-events: none;
    transition: 0.28s all ease-in-out;
    img{
      position: absolute;
      width: 100px;
      object-fit: contain;
    }
  }
  #hero_img_t{
    top: -100px;
  }
  #hero_img_b{
    bottom: -100px;
  }
  .hero-img-show-t{
    top: 0!important;
  }
  .hero-img-show-b{
    bottom: 0!important;
  }
  #hero_img_bLeft,#hero_img_bRight{
    bottom: 0;
  } 
  #hero_img_tLeft,#hero_img_tRight{
    transform: scaleY(-1);
    top: 0;
  } 
  #hero_img_bLeft, #hero_img_tLeft{
    left: 0;
  }
  #hero_img_bRight, #hero_img_tRight{
    transform: scaleX(-1);
    right: 0;
  }
  #hero_img_tRight{
    object-position: right;
    transform: scaleY(-1) scaleX(-1);
  }
</style>