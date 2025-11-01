<template>
  <!-- start home -->
  <div class="home">
    <div class="container">
      <!-- Text section -->
      <div class="text">
        <h1>حافظ على لياقتك وصحتك دائماً</h1>
        <p>انضم إلينا في جازان واستمتع بأفضل التدريبات والبرامج الرياضية</p>
        <div class="buttons-get-in-touch">
          <button>احجز استشارة</button>
          <button>تواصل معنا</button>
        </div>
      </div>

      <!-- Image slider section -->
      <div class="image-slider">
        <swiper
          ref="mySwiper"
          :loop="true"
          :autoplay="{ delay: 3000 }"
          class="mySwiper"
        >
          <swiper-slide><img src="../assets/1.jpg" /></swiper-slide>
          <swiper-slide><img src="../assets/3.jpg" /></swiper-slide>
          <swiper-slide><img src="../assets/4.jpg" /></swiper-slide>
          <swiper-slide><img src="../assets/5.jpg" /></swiper-slide>
        </swiper>

        <!-- Vertical arrows on right -->
        <div class="slider-buttons">
          <button @click="slidePrev"><i class="fa-solid fa-arrow-right-long"></i></button>
          <button @click="slideNext"><i class="fa-solid fa-arrow-down"></i></button>
        </div>
      </div>
    </div>
  </div>
  <!-- end home -->
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

export default {
  name: "HomePage",
  components: {
    Swiper,
    SwiperSlide,
  },
  methods: {
    slideNext() {
      this.$refs.mySwiper.swiper.slideNext();
    },
    slidePrev() {
      this.$refs.mySwiper.swiper.slidePrev();
    },
  },
};
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  margin-bottom: 10rem;
}

.container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 7rem;
  max-width: 1200px;
  width: 100%;
  flex-direction: row-reverse;
}

/* Text section */
.text {
  flex: 1;
  text-align: right;
}

.text h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  line-height: 1.3;
}

.text p {
  font-size: 1.2rem;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.buttons-get-in-touch button {
  margin-right: 1rem;
  padding: 0.8rem 1.5rem;
  font-size: 1rem;
  background-color: #ff6600;
  color: #fff;
  border: none;
  cursor: pointer;
  margin-top: 0.5rem;
  border-radius: 5px;
  transition: 0.3s;
}

.buttons-get-in-touch button:hover {
  background-color: #e65c00;
}

/* Image slider */
.image-slider {
  position: relative;
  flex: 1;
  max-width: 700px;
}

.image-slider img {
  width: 100%;
  height: auto;
  border-radius: 15px;
  object-fit: cover;
}

/* Vertical arrows on right side */
.slider-buttons {
  position: absolute;
  top: 50%;
  right: -60px;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  transform: translateY(-50%);
}

.slider-buttons button {
  background-color: #ff6600;
  border: none;
  color: white;
  font-size: 1.2rem;
  padding: 0.6rem 1rem;
  cursor: pointer;
  border-radius: 5px;
  transition: 0.3s;
}

.slider-buttons button:hover {
  background-color: #e65c00;
}

/* ---------------------- */
/* ✅ Responsive Design  */
/* ---------------------- */

/* Tablets and small laptops */
@media (max-width: 992px) {
  .container {
    flex-direction: column-reverse;
    gap: 3rem;
  }

  .text {
    text-align: center;
  }

  .text h1 {
    font-size: 2.4rem;
  }

  .text p {
    font-size: 1.1rem;
  }

  .buttons-get-in-touch button {
    margin-right: 0.5rem;
    font-size: 0.95rem;
  }

  .slider-buttons {
    right: 10px;
    flex-direction: row;
    top: auto;
    bottom: -50px;
    transform: none;
  }
}

/* Mobile large (e.g., Pixel 7, iPhone 14, etc.) */
@media (max-width: 600px) {
  .home {
    padding: 1.5rem 0.8rem;
  }

  .container {
    gap: 2rem;
  }

  .text h1 {
    font-size: 1.9rem;
  }

  .text p {
    font-size: 1rem;
  }

  .buttons-get-in-touch {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.8rem;
  }

  .buttons-get-in-touch button {
    width: 80%;
    font-size: 0.95rem;
  }

  .image-slider {
    max-width: 100%;
  }

  .slider-buttons {
    position: static;
    flex-direction: row;
    justify-content: center;
    margin-top: 1rem;
  }

  .slider-buttons button {
    font-size: 1rem;
    padding: 0.5rem 0.8rem;
  }
}

/* Very small screens */
@media (max-width: 400px) {
  .text h1 {
    font-size: 1.6rem;
  }

  .text p {
    font-size: 0.9rem;
  }

  .buttons-get-in-touch button {
    font-size: 0.85rem;
    width: 90%;
  }
}
</style>

