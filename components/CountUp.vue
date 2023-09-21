<template>
  <div ref="counterRef">
    <p class="number">
      {{ currentCount }}
    </p>
  </div>
</template>

<script setup>
const { count } = defineProps(["count"]);

const isInViewport = ref(false);
const currentCount = ref(0);
let intervalId;
const counterRef = ref(null);

const duration = 4000; // 4 seconds in milliseconds
const intervalDuration = duration / count; // Calculate interval duration

onMounted(() => {
  const options = {
    root: null, // Use the viewport as the root
    rootMargin: "0px",
    threshold: 0.5, // Trigger when at least 50% of the element is visible
  };

  const observer = new IntersectionObserver(handleIntersection, options);
  observer.observe(counterRef.value);
});

const handleIntersection = (entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      // The element is in the viewport
      isInViewport.value = true;
    }
  });
};

function incrementCount() {
  currentCount.value++;
  if (currentCount.value >= count) {
    stopCounting();
  }
}

function startCounting() {
  intervalId = setInterval(incrementCount, intervalDuration); // Use calculated interval duration
}

function stopCounting() {
  clearInterval(intervalId);
}

watch(isInViewport, (newValue) => {
  if (newValue) {
    startCounting();
  }
});

onUnmounted(() => {
  clearInterval(intervalId);
});
</script>
<style scoped>
.number {
  font-size: 40px;
  font-weight: 700;
}
</style>
