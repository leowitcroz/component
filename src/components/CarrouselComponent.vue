<template>
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentSlide * (100 / imagesPerPage)}%)` }">
        <div class="carousel-item" v-for="(slide, index) in slides" :key="index" :style="itemStyle">
          <img :src="slide.image" :alt="slide.alt" style="width: 100%; height: auto;">
        </div>
      </div>
      <button class="carousel-control-prev" @click="prevSlide">‹</button>
      <button class="carousel-control-next" @click="nextSlide">›</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed,defineProps  } from 'vue';
  
  const props = defineProps({
    slides: {
      type: Array,
      required: true
    },
    imagesPerPage: {
      type: Number,
      default: 3
    }
  });
  
  const currentSlide = ref(0);
  
  const totalSlides = computed(() => {
    return Math.ceil(props.slides.length - 1);  
  });
  
  const itemStyle = computed(() => {
    return {
      minWidth: `${100 / props.imagesPerPage}%`,  
      boxSizing: 'border-box'
    };
  });
  
  const nextSlide = () => {
    if (currentSlide.value < totalSlides.value - 1) {
      currentSlide.value++;
    } else {
      currentSlide.value = 0;  
    }
  };
  
  const prevSlide = () => {
    if (currentSlide.value > 0) {
      currentSlide.value--;
    } else {
      currentSlide.value = totalSlides.value - 1;  
    }
  };
  </script>
  
  <style scoped>
  .carousel {
    position: relative;
    width: 100%;
    overflow: hidden;
  }
  
  .carousel-inner {
    display: flex;
    transition: transform 0.5s ease;
  }
  
  .carousel-item {
    box-sizing: border-box;
  }
  
  .carousel-control-prev,
  .carousel-control-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    border: none;
    color: white;
    padding: 10px;
    cursor: pointer;
  }
  
  .carousel-control-prev {
    left: 10px;
  }
  
  .carousel-control-next {
    right: 10px;
  }
  </style>
  