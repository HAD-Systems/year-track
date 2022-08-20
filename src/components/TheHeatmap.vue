<template>
  <calendar-heatmap :end-date="2018 - 9 - 22" :values="[]" />
</template>

<script setup lang="ts">
import { CalendarHeatmap } from "vue3-calendar-heatmap";
import { onMounted } from "vue";

onMounted(() => {
  connectModalToDays();
});

function connectModalToDays() {
  const days = document.querySelectorAll(".vch__day__square");
  days.forEach((day) => {
    day.addEventListener("click", () => {
      console.log("clicked day", day);
    });
  });
}
</script>
