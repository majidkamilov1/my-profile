<template>
  <section class="projects">
    <div class="my-container">
      <h3>PROJECT'S</h3>
      <div class="projects-btns">
        <button @click="goPrev"><span><</span></button>
        <button @click="goNext"><span>></span></button>
      </div>
      <Swiper
        :slides-per-view="3"
        :space-between="30"
        :modules="modules"
        :loop="true"
        @swiper="onSwiper"
        class="mySwiper"
      >
        <swiper-slide v-for="(project, pIndex) in projects" :key="pIndex">
          <div class="projects-img">
            <img
              :src="project.images[project.currentIndex]"
              alt="project"
              class="project-image"
              @mouseenter="startRotation(project)"
              @mouseleave="stopRotation(project)"
            />
          </div>
          <div class="projects-text">
            <h4>
              <a :href="project.link">{{ project.name }}</a>
            </h4>
            <p>{{ project.description }}</p>
          </div>
        </swiper-slide>
      </Swiper>
    </div>
  </section>
</template>

<script setup>
import { reactive, onUnmounted, ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";

import "swiper/css";
import "swiper/css/navigation";

const modules = [Navigation, Pagination];

const swiperRef = ref(null);

const onSwiper = (swiper) => {
  swiperRef.value = swiper;
};

const goNext = () => {
  swiperRef.value?.slideNext();
};

const goPrev = () => {
  swiperRef.value?.slidePrev();
};

const projects = reactive([
  {
    name: "app.gapchy",
    link: "https://app.gapchy.com/",
    description: "",
    images: [
      "/images/project/gapchy/1.png",
      "/images/project/gapchy/2.png",
      "/images/project/gapchy/3.png",
      "/images/project/gapchy/4.png",
      "/images/project/gapchy/5.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "intex-cargo",
    link: "https://intex-cargo.com/",
    description: "",
    images: [
      "/images/project/intex-cargo/1.png",
      "/images/project/intex-cargo/2.png",
      "/images/project/intex-cargo/3.png",
      "/images/project/intex-cargo/4.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "maison",
    link: "https://maison.webmenu.online/",
    description: "",
    images: [
      "/images/project/maison/1.png",
      "/images/project/maison/2.png",
      "/images/project/maison/3.png",
      "/images/project/maison/4.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "jerdeshmoskva.ru",
    link: "https://jerdeshmoskva.ru/",
    description: "",
    images: [
      "/images/project/jerdesh/1.png",
      "/images/project/jerdesh/2.png",
      "/images/project/jerdesh/3.png",
      "/images/project/jerdesh/4.png",
      "/images/project/jerdesh/5.png",
      "/images/project/jerdesh/6.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "Enactus",
    link: "https://enactus.kg/",
    description: "",
    images: [
      "/images/project/enactus/1.png",
      "/images/project/enactus/2.png",
      "/images/project/enactus/3.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "alayky",
    link: "https://www.alaiku.com/?lightbox=dataItem-k8e4asdl5",
    description: "",
    images: [
      "/images/project/alayky/1.png",
      "/images/project/alayky/2.png",
      "/images/project/alayky/3.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "intex-cargo",
    link: "https://intex-cargo.com/",
    description: "",
    images: [
      "/images/project/intex-cargo/1.png",
      "/images/project/intex-cargo/2.png",
      "/images/project/intex-cargo/3.png",
      "/images/project/intex-cargo/4.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "Драмтеатр",
    link: "#",
    description: "",
    images: [
      "/images/project/драмтиатр/1.png",
      "/images/project/драмтиатр/2.png",
      "/images/project/драмтиатр/3.png",
      "/images/project/драмтиатр/4.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
  {
    name: "Мёд",
    link: "#",
    description: "",
    images: [
      "/images/project/мёд/1.png",
      "/images/project/мёд/2.png",
      "/images/project/мёд/3.png",
      "/images/project/мёд/4.png",
      "/images/project/мёд/5.png",
    ],
    currentIndex: 0,
    intervalId: null,
  },
]);

// Функции для каждого проекта
const startRotation = (project) => {
  if (project.intervalId) return;
  project.intervalId = setInterval(() => {
    project.currentIndex = (project.currentIndex + 1) % project.images.length;
  }, 1000);
};

const stopRotation = (project) => {
  clearInterval(project.intervalId);
  project.intervalId = null;
};

onUnmounted(() => {
  projects.forEach((p) => clearInterval(p.intervalId));
});
</script>

<style scoped>
.projects {
  background: linear-gradient(180deg, #000 0%, rgba(37, 37, 37, 0) 290%);
  background: linear-gradient(0deg, #000 0%, rgba(37, 37, 37, 0) 290%);

  > div {
    position: relative;
    padding: 32px 0;
    .projects-btns {
      display: flex;
      position: absolute;
      justify-content: space-between;
      width: 100%;

      top: 50%;
      gap: 30px;
      align-items: center;

      button {
        -webkit-box-shadow: -4px 11px 23px 0px rgba(34, 60, 80, 0.4);
        -moz-box-shadow: -4px 11px 23px 0px rgba(34, 60, 80, 0.4);
        box-shadow: -4px 11px 23px 0px rgba(34, 60, 80, 0.4);
        background: white;
        border: 1px solid #ffffff;
        border-radius: 100%;
        width: 40px;
        height: 40px;
        font-size: 20px;
        color: #000;
        cursor: pointer;
        transition:
          background-color 0.3s,
          color 0.3s;
        display: flex;
        justify-content: center;
        align-items: center;
        line-height: 30px;
        font-weight: 800;
        position: relative;
        z-index: 11;

        &:hover {
          background-color: #ffffff;
          color: #000000;
        }
      }
    }
    h3 {
      text-align: center;
      font-family: var(--font-family);
      font-weight: 700;
      font-size: 40px;
      line-height: 122%;
      letter-spacing: 0.15em;
      color: #fff;
      padding-bottom: 42px;
    }

    .mySwiper {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .projects-img {
      width: 100%;
      background: #000;
      border-radius: 30px;

      .project-image {
        border-radius: 30px;
        width: 100%;
        aspect-ratio: 4/3;
        border-radius: 12px;
        cursor: pointer;
        transition: opacity 0.4s ease;
        object-fit: cover;
      }
    }

    .projects-text {
      padding-top: 30px;
      text-align: center;

      h4 {
        color: white;
        font-family: var(--font-family);
        font-weight: 600;
        font-size: 20px;
        line-height: 150%;
        letter-spacing: 0.05em;
        &:hover {
          text-decoration: underline;
          color: rgb(15, 106, 180);
        }
      }

      p {
        font-family: var(--font-family);
        font-weight: 400;
        font-size: 16px;
        line-height: 150%;
        color: #ffffff;
        opacity: 0.7;
        margin-top: 12px;
      }
    }
  }
}
</style>
