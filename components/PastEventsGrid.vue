<template>
  <div class="section-container">
    <div class="past-grid-container">
      <div class="past-grid">
        <EventCard id="cowboy-icon" />
        <template v-for="year in years" :key="year">
          <EventCard :year="year" :theme="themes[year]" />
        </template>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import EventCard from '~/components/EventCard.vue';
export default {
  name: 'PastEventsGrid',
  components: { EventCard },
  data() {
    return {
      years: [2024, 2023, 2022, 2021, 2019, 2018, 2017, 2016, 2015, 2014] as const,
      themes: {
        2024: 'All About the Journey',
        2023: 'Find Your Frontier',
        2022: 'Adventure Awaits',
        2021: 'Explore Together',
        2019: 'Build With Purpose',
        2018: 'Mark Your Trail',
        2017: 'Build Together',
        2016: 'Explore New Grounds',
        2015: 'Imagine Tomorrow',
        2014: 'A New Hackathon',
      },
    };
  },
};
</script>

<style scoped>
#cowboy-icon {
  background-image: url('../assets/img/images/cowboy-hat.svg');
  background-repeat: no-repeat;
  background-size: 50% 50% !important;
}

.section-container {
  position: relative;
}

.past-grid-container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.past-grid {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  max-width: 100rem;
  padding: 0 3rem 0 3rem;
}

@keyframes bb-rotate {

  0%,
  100% {
    transform: rotate(-5deg);
  }

  50% {
    transform: rotate(-8deg);
  }
}

@keyframes circle-rotate {

  0%,
  100% {
    transform: rotate(-2deg);
  }

  50% {
    transform: rotate(2deg);
  }
}

.bb-rotate-div {
  animation: bb-rotate 8s ease infinite reverse;
}

.circle-rotate-div {
  animation: circle-rotate 8s ease infinite reverse;
}

.bob-div {
  animation: floatie-bob 6s ease infinite reverse;
}

.bb-floatie {
  width: 50vw;
  margin-left: -2vw;
  margin-bottom: -12vw;
}

.bb-floatie-text {
  position: absolute;
  transform: rotate(-20.5deg);
  font-size: 2.8vw;
  top: 13vw;
  left: 7.5vw;
}

.circle-floatie {
  width: 75vw;
  margin-left: 60vw;
  margin-top: -75vh;
  margin-bottom: -4vw;
}

/* mobile view */

/* bb floatie size */
@media (max-width: 768px) {
  .bb-floatie {
    width: 70vw;
    margin-left: -5vw;
    margin-bottom: -20vw;
  }

  .bb-floatie-text {
    font-size: 5vw;
    top: 17.5vw;
    left: 2.5vw;
  }
}

/* circle floatie position */
@media (max-width: 920px) {
  .circle-rotate-div {
    position: absolute;
    margin-top: 0;
    left: 0;
    top: 0vh;
  }

  .circle-floatie {
    width: 100vw;
    margin-top: 70vh;
  }
}
</style>
