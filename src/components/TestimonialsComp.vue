<template>
  <h1>Testimonials</h1>
    <div class="carousel-container">
      <div class="carousel">
        <div 
          v-for="(item, index) in carouselItems" 
          :key="index" 
          :class="getClass(index)"
          class="carousel__item"
        >
          <img :src="item.image" :alt="item.alt">
          <div class="carousel__text" v-if="index === currentIndex">
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
          </div>
        </div>
        <div class="carousel__btns">
          <button class="carousel__btn" @click="prevItem"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" fill-rule="evenodd" d="m15 4l2 2l-6 6l6 6l-2 2l-8-8z"/></svg></button>
          <button class="carousel__btn" @click="nextItem"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" fill-rule="evenodd" d="m9.005 4l8 8l-8 8L7 18l6.005-6L7 6z"/></svg></button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        currentIndex: 0,
      };
    },
    computed: {
      carouselItems() {
        return this.items;
      }
    },
    methods: {
      getClass(index) {
        if (index === this.currentIndex) {
          return 'carousel__item--main';
        } else if (index === (this.currentIndex + 1) % this.carouselItems.length) {
          return 'carousel__item--right';
        } else if (index === (this.currentIndex - 1 + this.carouselItems.length) % this.carouselItems.length) {
          return 'carousel__item--left';
        } else {
          return '';
        }
      },
      nextItem() {
        this.currentIndex = (this.currentIndex + 1) % this.carouselItems.length;
      },
      prevItem() {
        this.currentIndex = (this.currentIndex - 1 + this.carouselItems.length) % this.carouselItems.length;
      }
    }
  };
  </script>
  
  <style>
  /* Add your styles here */
  .carousel-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: calc(100vh - 150px); /* Increase the subtracted value to reduce the container's height */
  margin-bottom: 200px; /* Increase if necessary to ensure space for the footer */
}

  
  .carousel {
      position: relative;
  }
  .carousel__item {
  position: absolute;
  height: 30rem; /* Reduced from 35rem to make the item smaller */
  width: 20rem; /* Reduced from 25rem to make the item narrower */
  border-radius: 3px;
  overflow: hidden;
  box-shadow: 0 1rem 4rem rgba(0,0,0,.5);
  transform: translate(-50%, -50%) scale(.1);
  z-index: 0;
  transition: all .2s linear;
}
  .carousel__item img {
      width: 100%;
      min-height: 100%;
      object-fit: cover;
      background: #fff;
  }
  
  .carousel__item--main {
      transform: translate(-50%,-50%) scale(1);
      z-index: 2;
      cursor: pointer;
  }
  
  .carousel__item--left {
      transform: translate(-110%,-50%) scale(.9);
      z-index: 1;
  }
  .carousel__item--right {
      transform: translate(10%,-50%) scale(.9);
      z-index: 1;
  }
  .carousel__item--left img, .carousel__item--right img {
      filter: grayscale(80%);
  }
  
  .carousel__item--right:hover {
      transform: translate(10%,-50%) scale(1.2);
      z-index: 3;
      cursor: pointer;
  }
  .carousel__item--left:hover {
      transform: translate(-110%,-50%) scale(1.2);
      z-index: 3;
      cursor: pointer;
  }
  .carousel__item--main:hover {
      transform: translate(-50%,-50%) scale(1.2);
  }
  .carousel__item:hover > .carousel__text {
      opacity: 1;
  }
  .carousel__item:hover img {
      filter: grayscale(0%);
  }
  
  .carousel__text {
      position: absolute;
      bottom: 0;
      z-index: 4;
      opacity: 0;
      transition: opacity .2s;
      width: 100%;
      text-align: center;
      background-color: rgba(0,0,0,.5);
      padding: 2rem 1rem;
      color: #fff;
      opacity: 1;
  }
  
  
  .carousel__btns {
      position: absolute;
      transform: translate(-50%, 22rem);
      display: flex;
      gap: 2rem;
  }
  .carousel__btn {
      background-color: transparent;
      height: 5rem;
      width: 5rem;
      border-radius: 50%;
      border:1px solid currentColor;
      color: #fff;
      cursor: pointer;
  }
  .carousel__btn svg {
      height: 1.8rem;
      width: 1.8rem;
  }
  .carousel__btn:hover {
      color: #aaa;
  }
  </style>
  