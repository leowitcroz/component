<template>
  <div id="app">
    <CarrouselComponent :slides="slides" :imagesPerPage="2" />
  </div>
</template>

<script setup>
import CarrouselComponent from './components/CarrouselComponent.vue';

const slides = [
  { image: 'https://s2-techtudo.glbimg.com/L9wb1xt7tjjL-Ocvos-Ju0tVmfc=/0x0:1200x800/984x0/smart/filters:strip_icc()/i.s3.glbimg.com/v1/AUTH_08fbf48bc0524877943fe86e43087e7a/internal_photos/bs/2023/q/l/TIdfl2SA6J16XZAy56Mw/canvaai.png', alt: 'Slide 1' },
  { image: 'https://png.pngtree.com/thumb_back/fh260/background/20230605/pngtree-bright-colors-is-poured-into-a-black-background-image_2885679.jpg', alt: 'Slide 3' },
  { image: 'https://s2-techtudo.glbimg.com/L9wb1xt7tjjL-Ocvos-Ju0tVmfc=/0x0:1200x800/984x0/smart/filters:strip_icc()/i.s3.glbimg.com/v1/AUTH_08fbf48bc0524877943fe86e43087e7a/internal_photos/bs/2023/q/l/TIdfl2SA6J16XZAy56Mw/canvaai.png', alt: 'Slide 1' },
  { image: 'https://png.pngtree.com/thumb_back/fh260/background/20230605/pngtree-bright-colors-is-poured-into-a-black-background-image_2885679.jpg', alt: 'Slide 3' },
  { image: 'https://www.designi.com.br/images/preview/10073442.jpg', alt: 'Slide 3' },
  { image: 'https://www.designi.com.br/images/preview/10073442.jpg', alt: 'Slide 3' },
]

</script>

<style>

</style>