<template>
  <section class="skills">
    <div class="my-container">
      <h3>SKILLS</h3>

      <swiper
        :slides-per-view="3"
        :space-between="30"
        :pagination="{ clickable: true }"
        class="mySwiper"
      >
        <swiper-slide v-for="(skill, index) in skills" :key="index">
          <div class="circle-wrapper">
            <svg class="circle-progress" viewBox="0 0 36 36">
              <path
                class="bg"
                d="M18 2.0845
                                 a 15.9155 15.9155 0 0 1 0 31.831
                                 a 15.9155 15.9155 0 0 1 0 -31.831"
              />
              <path
                class="progress"
                :stroke-dasharray="skill.animatedValue + ', 100'"
                d="M18 2.0845
                                 a 15.9155 15.9155 0 0 1 0 31.831
                                 a 15.9155 15.9155 0 0 1 0 -31.831"
              />
            </svg>
            <div class="percent-text">{{ skill.displayValue }}%</div>
          </div>

          <div class="skills-text">
            <h4>{{ skill.name }}</h4>
            <p>{{ skill.description }}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<script setup>
import { reactive, onMounted } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";

const skills = reactive([
  {
    name: "Python Programming",
    value: 75,
    displayValue: 0,
    animatedValue: 0,
    description: "Python Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "C Programming",
    value: 70,
    displayValue: 0,
    animatedValue: 0,
    description: "C Programming",
  },
  {
    name: "Java Programming",
    value: 40,
    displayValue: 0,
    animatedValue: 0,
    description: "Java Programming",
  },
]);

const animateSkill = (skill) => {
  const duration = 1500; // 1.5 сек
  const start = performance.now();

  const animate = (time) => {
    const progress = Math.min((time - start) / duration, 1);
    skill.displayValue = Math.floor(progress * skill.value); // число
    skill.animatedValue = progress * skill.value; // для stroke-dasharray

    if (progress < 1) requestAnimationFrame(animate);
  };

  requestAnimationFrame(animate);
};

onMounted(() => {
  skills.forEach((skill) => animateSkill(skill));
});
</script>

<style scoped>
.skills {
    padding-top: 60px;
    padding-bottom: 60px;
    background: linear-gradient(180deg, #000 0%, rgba(37, 37, 37, 0) 290%);
  /* background: linear-gradient(0deg, #000 0%, rgba(37, 37, 37, 0) 290%); */
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
}
.circle-wrapper {
  position: relative;
  width: 140px;
  height: 140px;
  margin: 0 auto;
}

.circle-progress {
  width: 100%;
  height: 100%;
  transform: rotate(-0deg);
}

.circle-progress .bg {
  fill: none;
  stroke: #222;
  stroke-width: 2.8;
}

.circle-progress .progress {
  fill: none;
  stroke: #fff;
  stroke-width: 2.8;
  stroke-linecap: round;
  transition: stroke-dasharray 0.5s ease;
}

.percent-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 22px;
  font-weight: 700;
  color: #fff;
}
</style>
