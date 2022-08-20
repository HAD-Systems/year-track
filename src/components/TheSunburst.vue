<script setup lang="ts">
import { onMounted } from "vue";
import * as d3 from "d3";

onMounted(() => {
  init();
});

function init() {
  // set the dimensions and margins of the graph
  const width = window.innerWidth;
  const height = window.innerHeight;
  const radius = Math.min(width, height) / 1.4 / 3;

  const data = {
    name: "Year",
    children: [
      {
        name: "January",
        children: [
          { name: "1st - Saturday", value: 1, completed: true, content: {} },
          { name: "2nd - Sunday", value: 1, completed: true, content: {} },
          { name: "3rd - Monday", value: 1, completed: true, content: {} },
          { name: "4th - Tuesday", value: 1, completed: true, content: {} },
          { name: "5th - Wednesday", value: 1, completed: true, content: {} },
          { name: "6th - Thursday", value: 1, completed: true, content: {} },
          { name: "7th - Friday", value: 1, completed: true, content: {} },
          { name: "8th - Saturday", value: 1, completed: true, content: {} },
          { name: "9th - Sunday", value: 1, completed: true, content: {} },
          { name: "10th - Monday", value: 1, completed: true, content: {} },
          { name: "11th - Tuesday", value: 1, completed: true, content: {} },
          { name: "12th - Wednesday", value: 1, completed: true, content: {} },
          { name: "13th - Thursday", value: 1, completed: true, content: {} },
          { name: "14th - Friday", value: 1, completed: true, content: {} },
          { name: "15th - Saturday", value: 1, completed: true, content: {} },
          { name: "16th - Sunday", value: 1, completed: true, content: {} },
          { name: "17th - Monday", value: 1, completed: true, content: {} },
          { name: "18th - Tuesday", value: 1, completed: true, content: {} },
          { name: "19th - Wednesday", value: 1, completed: true, content: {} },
          { name: "20th - Thursday", value: 1, completed: true, content: {} },
          { name: "21st - Friday", value: 1, completed: true, content: {} },
          { name: "22nd - Saturday", value: 1, completed: true, content: {} },
          { name: "23rd - Sunday", value: 1, completed: true, content: {} },
          { name: "24th - Monday", value: 1, completed: true, content: {} },
          { name: "25th - Tuesday", value: 1, completed: true, content: {} },
          { name: "26th - Wednesday", value: 1, completed: true, content: {} },
          { name: "27th - Thursday", value: 1, completed: true, content: {} },
          { name: "28th - Friday", value: 1, completed: true, content: {} },
          { name: "29th - Saturday", value: 1, completed: true, content: {} },
          { name: "30th - Sunday", value: 1, completed: true, content: {} },
          { name: "31st - Monday", value: 1, completed: true, content: {} },
        ],
      },

      {
        name: "February",
        children: [
          { name: "1st - Tuesday", value: 1, completed: true, content: {} },
          { name: "2nd - Wednesday", value: 1, completed: true, content: {} },
          { name: "3rd - Thursday", value: 1, completed: true, content: {} },
          { name: "4th - Friday", value: 1, completed: true, content: {} },
          { name: "5th - Saturday", value: 1, completed: true, content: {} },
          { name: "6th - Sunday", value: 1, completed: true, content: {} },
          { name: "7th - Monday", value: 1, completed: true, content: {} },
          { name: "8th - Tuesday", value: 1, completed: true, content: {} },
          { name: "9th - Wednesday", value: 1, completed: true, content: {} },
          { name: "10th - Thursday", value: 1, completed: true, content: {} },
          { name: "11th - Friday", value: 1, completed: true, content: {} },
          { name: "12th - Saturday", value: 1, completed: true, content: {} },
          { name: "13th - Sunday", value: 1, completed: true, content: {} },
          { name: "14th - Monday", value: 1, completed: true, content: {} },
          { name: "15th - Tuesday", value: 1, completed: true, content: {} },
          { name: "16th - Wednesday", value: 1, completed: true, content: {} },
          { name: "17th - Thursday", value: 1, completed: true, content: {} },
          { name: "18th - Friday", value: 1, completed: true, content: {} },
          { name: "19th - Saturday", value: 1, completed: true, content: {} },
          { name: "20th - Sunday", value: 1, completed: true, content: {} },
          { name: "21st - Monday", value: 1, completed: true, content: {} },
          { name: "22nd - Tuesday", value: 1, completed: true, content: {} },
          { name: "23rd - Wednesday", value: 1, completed: true, content: {} },
          { name: "24th - Thursday", value: 1, completed: true, content: {} },
          { name: "25th - Friday", value: 1, completed: true, content: {} },
          { name: "26th - Saturday", value: 1, completed: true, content: {} },
          { name: "27th - Sunday", value: 1, completed: true, content: {} },
          { name: "28th - Monday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "March",
        children: [
          { name: "1st - Tuesday", value: 1, completed: true, content: {} },
          { name: "2nd - Wednesday", value: 1, completed: true, content: {} },
          { name: "3rd - Thursday", value: 1, completed: true, content: {} },
          { name: "4th - Friday", value: 1, completed: true, content: {} },
          { name: "5th - Saturday", value: 1, completed: true, content: {} },
          { name: "6th - Sunday", value: 1, completed: true, content: {} },
          { name: "7th - Monday", value: 1, completed: true, content: {} },
          { name: "8th - Tuesday", value: 1, completed: true, content: {} },
          { name: "9th - Wednesday", value: 1, completed: true, content: {} },
          { name: "10th - Thursday", value: 1, completed: true, content: {} },
          { name: "11th - Friday", value: 1, completed: true, content: {} },
          { name: "12th - Saturday", value: 1, completed: true, content: {} },
          { name: "13th - Sunday", value: 1, completed: true, content: {} },
          { name: "14th - Monday", value: 1, completed: true, content: {} },
          { name: "15th - Tuesday", value: 1, completed: true, content: {} },
          { name: "16th - Wednesday", value: 1, completed: true, content: {} },
          { name: "17th - Thursday", value: 1, completed: true, content: {} },
          { name: "18th - Friday", value: 1, completed: true, content: {} },
          { name: "19th - Saturday", value: 1, completed: true, content: {} },
          { name: "20th - Sunday", value: 1, completed: true, content: {} },
          { name: "21st - Monday", value: 1, completed: true, content: {} },
          { name: "22nd - Tuesday", value: 1, completed: true, content: {} },
          { name: "23rd - Wednesday", value: 1, completed: true, content: {} },
          { name: "24th - Thursday", value: 1, completed: true, content: {} },
          { name: "25th - Friday", value: 1, completed: true, content: {} },
          { name: "26th - Saturday", value: 1, completed: true, content: {} },
          { name: "27th - Sunday", value: 1, completed: true, content: {} },
          { name: "28th - Monday", value: 1, completed: true, content: {} },
          { name: "29th - Tuesday", value: 1, completed: true, content: {} },
          { name: "30th - Wednesday", value: 1, completed: true, content: {} },
          { name: "31st - Thursday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "April",
        children: [
          { name: "1st - Friday", value: 1, completed: true, content: {} },
          { name: "2nd - Saturday", value: 1, completed: true, content: {} },
          { name: "3rd - Sunday", value: 1, completed: true, content: {} },
          { name: "4th - Monday", value: 1, completed: true, content: {} },
          { name: "5th - Tuesday", value: 1, completed: true, content: {} },
          { name: "6th - Wednesday", value: 1, completed: true, content: {} },
          { name: "7th - Thursday", value: 1, completed: true, content: {} },
          { name: "8th - Friday", value: 1, completed: true, content: {} },
          { name: "9th - Saturday", value: 1, completed: true, content: {} },
          { name: "10th - Sunday", value: 1, completed: true, content: {} },
          { name: "11th - Monday", value: 1, completed: true, content: {} },
          { name: "12th - Tuesday", value: 1, completed: true, content: {} },
          { name: "13th - Wednesday", value: 1, completed: true, content: {} },
          { name: "14th - Thursday", value: 1, completed: true, content: {} },
          { name: "15th - Friday", value: 1, completed: true, content: {} },
          { name: "16th - Saturday", value: 1, completed: true, content: {} },
          { name: "17th - Sunday", value: 1, completed: true, content: {} },
          { name: "18th - Monday", value: 1, completed: true, content: {} },
          { name: "19th - Tuesday", value: 1, completed: true, content: {} },
          { name: "20th - Wednesday", value: 1, completed: true, content: {} },
          { name: "21st - Thursday", value: 1, completed: true, content: {} },
          { name: "22nd - Friday", value: 1, completed: true, content: {} },
          { name: "23rd - Saturday", value: 1, completed: true, content: {} },
          { name: "24th - Sunday", value: 1, completed: true, content: {} },
          { name: "25th - Monday", value: 1, completed: true, content: {} },
          { name: "26th - Tuesday", value: 1, completed: true, content: {} },
          { name: "27th - Wednesday", value: 1, completed: true, content: {} },
          { name: "28th - Thursday", value: 1, completed: true, content: {} },
          { name: "29th - Friday", value: 1, completed: true, content: {} },
          { name: "30th - Saturday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "May",
        children: [
          { name: "1st - Sunday", value: 1, completed: true, content: {} },
          { name: "2nd - Monday", value: 1, completed: true, content: {} },
          { name: "3rd - Tuesday", value: 1, completed: true, content: {} },
          { name: "4th - Wednesday", value: 1, completed: true, content: {} },
          { name: "5th - Thursday", value: 1, completed: true, content: {} },
          { name: "6th - Friday", value: 1, completed: true, content: {} },
          { name: "7th - Saturday", value: 1, completed: true, content: {} },
          { name: "8th - Sunday", value: 1, completed: true, content: {} },
          { name: "9th - Monday", value: 1, completed: true, content: {} },
          { name: "10th - Tuesday", value: 1, completed: true, content: {} },
          { name: "11th - Wednesday", value: 1, completed: true, content: {} },
          { name: "12th - Thursday", value: 1, completed: true, content: {} },
          { name: "13th - Friday", value: 1, completed: true, content: {} },
          { name: "14th - Saturday", value: 1, completed: true, content: {} },
          { name: "15th - Sunday", value: 1, completed: true, content: {} },
          { name: "16th - Monday", value: 1, completed: true, content: {} },
          { name: "17th - Tuesday", value: 1, completed: true, content: {} },
          { name: "18th - Wednesday", value: 1, completed: true, content: {} },
          { name: "19th - Thursday", value: 1, completed: true, content: {} },
          { name: "20th - Friday", value: 1, completed: true, content: {} },
          { name: "21st - Saturday", value: 1, completed: true, content: {} },
          { name: "22nd - Sunday", value: 1, completed: true, content: {} },
          { name: "23rd - Monday", value: 1, completed: true, content: {} },
          { name: "24th - Tuesday", value: 1, completed: true, content: {} },
          { name: "25th - Wednesday", value: 1, completed: true, content: {} },
          { name: "26th - Thursday", value: 1, completed: true, content: {} },
          { name: "27th - Friday", value: 1, completed: true, content: {} },
          { name: "28th - Saturday", value: 1, completed: true, content: {} },
          { name: "29th - Sunday", value: 1, completed: true, content: {} },
          { name: "30st - Monday", value: 1, completed: true, content: {} },
          { name: "31st - Tuesday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "June",
        children: [
          { name: "1st - Wednesday", value: 1, completed: true, content: {} },
          { name: "2nd - Thursday", value: 1, completed: true, content: {} },
          { name: "3rd - Friday", value: 1, completed: true, content: {} },
          { name: "4th - Saturday", value: 1, completed: true, content: {} },
          { name: "5th - Sunday", value: 1, completed: true, content: {} },
          { name: "6th - Monday", value: 1, completed: true, content: {} },
          { name: "7th - Tuesday", value: 1, completed: true, content: {} },
          { name: "8th - Wednesday", value: 1, completed: true, content: {} },
          { name: "9th - Thursday", value: 1, completed: true, content: {} },
          { name: "10th - Friday", value: 1, completed: true, content: {} },
          { name: "11th - Saturday", value: 1, completed: true, content: {} },
          { name: "12th - Sunday", value: 1, completed: true, content: {} },
          { name: "13th - Monday", value: 1, completed: true, content: {} },
          { name: "14th - Tuesday", value: 1, completed: true, content: {} },
          { name: "15th - Wednesday", value: 1, completed: true, content: {} },
          { name: "16th - Thursday", value: 1, completed: true, content: {} },
          { name: "17th - Friday", value: 1, completed: true, content: {} },
          { name: "18th - Saturday", value: 1, completed: true, content: {} },
          { name: "19th - Sunday", value: 1, completed: true, content: {} },
          { name: "20th - Monday", value: 1, completed: true, content: {} },
          { name: "21st - Tuesday", value: 1, completed: true, content: {} },
          { name: "22nd - Wednesday", value: 1, completed: true, content: {} },
          { name: "23rd - Thursday", value: 1, completed: true, content: {} },
          { name: "24th - Friday", value: 1, completed: true, content: {} },
          { name: "25th - Saturday", value: 1, completed: true, content: {} },
          { name: "26th - Sunday", value: 1, completed: true, content: {} },
          { name: "27th - Monday", value: 1, completed: true, content: {} },
          { name: "28th - Tuesday", value: 1, completed: true, content: {} },
          { name: "29th - Wednesday", value: 1, completed: true, content: {} },
          { name: "30th - Thursday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "July",
        children: [
          { name: "1st - Friday", value: 1, completed: true, content: {} },
          { name: "2nd - Saturday", value: 1, completed: true, content: {} },
          { name: "3rd - Sunday", value: 1, completed: true, content: {} },
          { name: "4th - Monday", value: 1, completed: true, content: {} },
          { name: "5th - Tuesday", value: 1, completed: true, content: {} },
          { name: "6th - Wednesday", value: 1, completed: true, content: {} },
          { name: "7th - Thursday", value: 1, completed: true, content: {} },
          { name: "8th - Friday", value: 1, completed: true, content: {} },
          { name: "9th - Saturday", value: 1, completed: true, content: {} },
          { name: "10th - Sunday", value: 1, completed: true, content: {} },
          { name: "11th - Monday", value: 1, completed: true, content: {} },
          { name: "12th - Tuesday", value: 1, completed: true, content: {} },
          { name: "13th - Wednesday", value: 1, completed: true, content: {} },
          { name: "14th - Thursday", value: 1, completed: true, content: {} },
          { name: "15th - Friday", value: 1, completed: true, content: {} },
          { name: "16th - Saturday", value: 1, completed: true, content: {} },
          { name: "17th - Sunday", value: 1, completed: true, content: {} },
          { name: "18th - Monday", value: 1, completed: true, content: {} },
          { name: "19th - Tuesday", value: 1, completed: true, content: {} },
          { name: "20th - Wednesday", value: 1, completed: true, content: {} },
          { name: "21st - Thursday", value: 1, completed: true, content: {} },
          { name: "22nd - Friday", value: 1, completed: true, content: {} },
          { name: "23rd - Saturday", value: 1, completed: true, content: {} },
          { name: "24th - Sunday", value: 1, completed: true, content: {} },
          { name: "25th - Monday", value: 1, completed: true, content: {} },
          { name: "26th - Tuesday", value: 1, completed: true, content: {} },
          { name: "27th - Wednesday", value: 1, completed: true, content: {} },
          { name: "28th - Thursday", value: 1, completed: true, content: {} },
          { name: "29th - Friday", value: 1, completed: true, content: {} },
          { name: "30th - Saturday", value: 1, completed: true, content: {} },
          { name: "31st - Sunday", value: 1, completed: true, content: {} },
        ],
      },
      {
        name: "August",
        children: [
          { name: "1st - Monday", value: 1, completed: true, content: {} },
          { name: "2nd - Tuesday", value: 1, completed: true, content: {} },
          { name: "3rd - Wednesday", value: 1, completed: true, content: {} },
          { name: "4th - Thursday", value: 1, completed: true, content: {} },
          { name: "5th - Friday", value: 1, completed: true, content: {} },
          { name: "6th - Saturday", value: 1, completed: true, content: {} },
          { name: "7th - Sunday", value: 1, completed: true, content: {} },
          { name: "8th - Monday", value: 1, completed: true, content: {} },
          { name: "9th - Tuesday", value: 1, completed: true, content: {} },
          { name: "10th - Wednesday", value: 1, completed: true, content: {} },
          { name: "11th - Thursday", value: 1, completed: true, content: {} },
          { name: "12th - Friday", value: 1, completed: true, content: {} },
          { name: "13th - Saturday", value: 1, completed: true, content: {} },
          { name: "14th - Sunday", value: 1, completed: true, content: {} },
          { name: "15th - Monday", value: 1, completed: true, content: {} },
          { name: "16th - Tuesday", value: 1, completed: false, content: {} },
          { name: "17th - Wednesday", value: 1, completed: false, content: {} },
          { name: "18th - Thursday", value: 1, completed: false, content: {} },
          { name: "19th - Friday", value: 1, completed: false, content: {} },
          { name: "20th - Saturday", value: 1, completed: false, content: {} },
          { name: "21st - Sunday", value: 1, completed: false, content: {} },
          { name: "22nd - Monday", value: 1, completed: false, content: {} },
          { name: "23rd - Tuesday", value: 1, completed: false, content: {} },
          { name: "24th - Wednesday", value: 1, completed: false, content: {} },
          { name: "25th - Thursday", value: 1, completed: false, content: {} },
          { name: "26th - Friday", value: 1, completed: false, content: {} },
          { name: "27th - Saturday", value: 1, completed: false, content: {} },
          { name: "28th - Sunday", value: 1, completed: false, content: {} },
          { name: "29th - Monday", value: 1, completed: false, content: {} },
          { name: "30th - Tuesday", value: 1, completed: false, content: {} },
          { name: "31st - Wednesday", value: 1, completed: false, content: {} },
        ],
      },
      {
        name: "September",
        children: [
          { name: "1st - Thursday", value: 1, completed: false, content: {} },
          { name: "2nd - Friday", value: 1, completed: false, content: {} },
          { name: "3rd - Saturday", value: 1, completed: false, content: {} },
          { name: "4th - Sunday", value: 1, completed: false, content: {} },
          { name: "5th - Monday", value: 1, completed: false, content: {} },
          { name: "6th - Tuesday", value: 1, completed: false, content: {} },
          { name: "7th - Wednesday", value: 1, completed: false, content: {} },
          { name: "8th - Thursday", value: 1, completed: false, content: {} },
          { name: "9th - Friday", value: 1, completed: false, content: {} },
          { name: "10th - Saturday", value: 1, completed: false, content: {} },
          { name: "11th - Sunday", value: 1, completed: false, content: {} },
          { name: "12th - Monday", value: 1, completed: false, content: {} },
          { name: "13th - Tuesday", value: 1, completed: false, content: {} },
          { name: "14th - Wednesday", value: 1, completed: false, content: {} },
          { name: "15th - Thursday", value: 1, completed: false, content: {} },
          { name: "16th - Friday", value: 1, completed: false, content: {} },
          { name: "17th - Saturday", value: 1, completed: false, content: {} },
          { name: "18th - Sunday", value: 1, completed: false, content: {} },
          { name: "19th - Monday", value: 1, completed: false, content: {} },
          { name: "20th - Tuesday", value: 1, completed: false, content: {} },
          { name: "21st - Wednesday", value: 1, completed: false, content: {} },
          { name: "22nd - Thursday", value: 1, completed: false, content: {} },
          { name: "23rd - Friday", value: 1, completed: false, content: {} },
          { name: "24th - Saturday", value: 1, completed: false, content: {} },
          { name: "25th - Sunday", value: 1, completed: false, content: {} },
          { name: "26th - Monday", value: 1, completed: false, content: {} },
          { name: "27th - Tuesday", value: 1, completed: false, content: {} },
          { name: "28th - Wednesday", value: 1, completed: false, content: {} },
          { name: "29th - Thursday", value: 1, completed: false, content: {} },
          { name: "30th - Friday", value: 1, completed: false, content: {} },
        ],
      },
      {
        name: "October",
        children: [
          { name: "1st - Saturday", value: 1, completed: false, content: {} },
          { name: "2nd - Sunday", value: 1, completed: false, content: {} },
          { name: "3rd - Monday", value: 1, completed: false, content: {} },
          { name: "4th - Tuesday", value: 1, completed: false, content: {} },
          { name: "5th - Wednesday", value: 1, completed: false, content: {} },
          { name: "6th - Thursday", value: 1, completed: false, content: {} },
          { name: "7th - Friday", value: 1, completed: false, content: {} },
          { name: "8th - Saturday", value: 1, completed: false, content: {} },
          { name: "9th - Sunday", value: 1, completed: false, content: {} },
          { name: "10th - Monday", value: 1, completed: false, content: {} },
          { name: "11th - Tuesday", value: 1, completed: false, content: {} },
          { name: "12th - Wednesday", value: 1, completed: false, content: {} },
          { name: "13th - Thursday", value: 1, completed: false, content: {} },
          { name: "14th - Friday", value: 1, completed: false, content: {} },
          { name: "15th - Saturday", value: 1, completed: false, content: {} },
          { name: "16th - Sunday", value: 1, completed: false, content: {} },
          { name: "17th - Monday", value: 1, completed: false, content: {} },
          { name: "18th - Tuesday", value: 1, completed: false, content: {} },
          { name: "19th - Wednesday", value: 1, completed: false, content: {} },
          { name: "20th - Thursday", value: 1, completed: false, content: {} },
          { name: "21st - Friday", value: 1, completed: false, content: {} },
          { name: "22nd - Saturday", value: 1, completed: false, content: {} },
          { name: "23rd - Sunday", value: 1, completed: false, content: {} },
          { name: "24th - Monday", value: 1, completed: false, content: {} },
          { name: "25th - Tuesday", value: 1, completed: false, content: {} },
          { name: "26th - Wednesday", value: 1, completed: false, content: {} },
          { name: "27th - Thursday", value: 1, completed: false, content: {} },
          { name: "28th - Friday", value: 1, completed: false, content: {} },
          { name: "29nd - Saturday", value: 1, completed: false, content: {} },
          { name: "30th - Sunday", value: 1, completed: false, content: {} },
          { name: "31st - Monday", value: 1, completed: false, content: {} },
        ],
      },

      {
        name: "November",
        children: [
          { name: "1st - Tuesday", value: 1, completed: false, content: {} },
          { name: "2nd - Wednesday", value: 1, completed: false, content: {} },
          { name: "3rd - Thursday", value: 1, completed: false, content: {} },
          { name: "4th - Friday", value: 1, completed: false, content: {} },
          { name: "5th - Saturday", value: 1, completed: false, content: {} },
          { name: "6th - Sunday", value: 1, completed: false, content: {} },
          { name: "7th - Monday", value: 1, completed: false, content: {} },
          { name: "8th - Tuesday", value: 1, completed: false, content: {} },
          { name: "9th - Wednesday", value: 1, completed: false, content: {} },
          { name: "10th - Thursday", value: 1, completed: false, content: {} },
          { name: "11th - Friday", value: 1, completed: false, content: {} },
          { name: "12th - Saturday", value: 1, completed: false, content: {} },
          { name: "13th - Sunday", value: 1, completed: false, content: {} },
          { name: "14th - Monday", value: 1, completed: false, content: {} },
          { name: "15th - Tuesday", value: 1, completed: false, content: {} },
          { name: "16th - Wednesday", value: 1, completed: false, content: {} },
          { name: "17th - Thursday", value: 1, completed: false, content: {} },
          { name: "18th - Friday", value: 1, completed: false, content: {} },
          { name: "19th - Saturday", value: 1, completed: false, content: {} },
          { name: "20th - Sunday", value: 1, completed: false, content: {} },
          { name: "21st - Monday", value: 1, completed: false, content: {} },
          { name: "22nd - Tuesday", value: 1, completed: false, content: {} },
          { name: "23rd - Wednesday", value: 1, completed: false, content: {} },
          { name: "24th - Thursday", value: 1, completed: false, content: {} },
          { name: "25th - Friday", value: 1, completed: false, content: {} },
          { name: "26th - Saturday", value: 1, completed: false, content: {} },
          { name: "27th - Sunday", value: 1, completed: false, content: {} },
          { name: "28th - Monday", value: 1, completed: false, content: {} },
          { name: "29th - Tuesday", value: 1, completed: false, content: {} },
          { name: "30th - Wednesday", value: 1, completed: false, content: {} },
        ],
      },
      {
        name: "December",
        children: [
          { name: "1st - Thursday", value: 1, completed: false, content: {} },
          { name: "2nd - Friday", value: 1, completed: false, content: {} },
          { name: "3rd - Saturday", value: 1, completed: false, content: {} },
          { name: "4th - Sunday", value: 1, completed: false, content: {} },
          { name: "5th - Monday", value: 1, completed: false, content: {} },
          { name: "6th - Tuesday", value: 1, completed: false, content: {} },
          { name: "7th - Wednesday", value: 1, completed: false, content: {} },
          { name: "8th - Thursday", value: 1, completed: false, content: {} },
          { name: "9th - Friday", value: 1, completed: false, content: {} },
          { name: "10th - Saturday", value: 1, completed: false, content: {} },
          { name: "11th - Sunday", value: 1, completed: false, content: {} },
          { name: "12th - Monday", value: 1, completed: false, content: {} },
          { name: "13th - Tuesday", value: 1, completed: false, content: {} },
          { name: "14th - Wednesday", value: 1, completed: false, content: {} },
          { name: "15th - Thursday", value: 1, completed: false, content: {} },
          { name: "16th - Friday", value: 1, completed: false, content: {} },
          { name: "17th - Saturday", value: 1, completed: false, content: {} },
          { name: "18th - Sunday", value: 1, completed: false, content: {} },
          { name: "19th - Monday", value: 1, completed: false, content: {} },
          { name: "20th - Tuesday", value: 1, completed: false, content: {} },
          { name: "21st - Wednesday", value: 1, completed: false, content: {} },
          { name: "22nd - Thursday", value: 1, completed: false, content: {} },
          { name: "23rd - Friday", value: 1, completed: false, content: {} },
          { name: "24th - Saturday", value: 1, completed: false, content: {} },
          { name: "25th - Sunday", value: 1, completed: false, content: {} },
          { name: "26th - Monday", value: 1, completed: false, content: {} },
          { name: "27th - Tuesday", value: 1, completed: false, content: {} },
          { name: "28th - Wednesday", value: 1, completed: false, content: {} },
          { name: "29th - Thursday", value: 1, completed: false, content: {} },
          { name: "30th - Friday", value: 1, completed: false, content: {} },
          { name: "32st - Saturday", value: 1, completed: false, content: {} },
        ],
      },
    ],
  };

  const partition = (data: any) => {
    const root = d3.hierarchy(data).sum((d: any) => d.value);
    // .sort((a, b) => b.value - a.value);
    return d3.partition().size([2 * Math.PI, root.height + 1])(root);
  };

  // set the color scale
  //   color = d3.scaleOrdinal(d3.quantize(d3.interpolateRainbow, data.children.length + 1))
  //   color = d3.scaleOrdinal(d3.quantize(d3.interpolateHcl("#679", "#179"), data.children.length))
  const color = d3.scaleOrdinal(["#eeeed7", "#eed7d7"]);

  const format = d3.format(",d");

  const arc = d3
    .arc()
    .startAngle((d) => d.x0)
    .endAngle((d) => d.x1)
    .padAngle((d) => Math.min((d.x1 - d.x0) / 2, 0.005))
    .padRadius(radius * 1.5)
    .innerRadius((d) => d.y0 * radius)
    .outerRadius((d) => Math.max(d.y0 * radius, d.y1 * radius - 1));

  const root = partition(data);

  root.each((d) => (d.current = d));

  // append the svg object to the div called 'dataviz'
  const svg = d3
    .select("#dataviz")
    .append("svg")
    .attr("viewBox", [0, 0, width, width])
    .style("font", "16px sans-serif");

  const g = svg
    .append("g")
    .attr("transform", `translate(${width / 2},${width / 2.65})`);

  const path = g
    .append("g")
    .selectAll("path")
    .data(root.descendants().slice(1))
    .join("path")
    .attr("fill", (d) => {
      while (d.depth > 1) d = d.parent;
      return color(d.data.name);
    })
    .attr("fill-opacity", (d) =>
      arcVisible(d.current) ? (d.children ? 0.5 : 1) : 0
    )
    .attr("pointer-events", (d) => (arcVisible(d.current) ? "auto" : "none"))

    .attr("d", (d) => arc(d.current));

  // path.filter(d => d.children)
  path.style("cursor", "pointer").on("click", clicked);

  path.append("title").text(
    (d) =>
      `${d
        .ancestors()
        .map((d) => d.data.name)
        .reverse()
        .join("/")}\n${format(d.value)}`
  );

  const label = g
    .append("g")
    .attr("pointer-events", "none")
    .attr("text-anchor", "middle")
    .style("user-select", "none")
    .selectAll("text")
    .data(root.descendants().slice(1))
    .join("text")
    .attr("dy", "0.35em")
    .attr("font-size", "25px")
    .attr("fill-opacity", (d) => +labelVisible(d.current))
    .attr("transform", (d) => labelTransform(d.current))
    .text((d) => d.data.name);

  const parent = g
    .append("circle")
    .datum(root)
    .attr("r", radius)
    .attr("fill", "none")
    .attr("pointer-events", "all")
    .on("click", clicked);

  function clicked(event, p) {
    console.log("click", p);

    if (p.children) {
      parent.datum(p.parent || root);

      root.each(
        (d) =>
          (d.target = {
            x0:
              Math.max(0, Math.min(1, (d.x0 - p.x0) / (p.x1 - p.x0))) *
              2 *
              Math.PI,
            x1:
              Math.max(0, Math.min(1, (d.x1 - p.x0) / (p.x1 - p.x0))) *
              2 *
              Math.PI,
            y0: Math.max(0, d.y0 - p.depth),
            y1: Math.max(0, d.y1 - p.depth),
          })
      );

      const t = g.transition().duration(750);

      // Transition the data on all arcs, even the ones that aren’t visible,
      // so that if this transition is interrupted, entering arcs will start
      // the next transition from the desired position.
      path
        .transition(t)
        .tween("data", (d) => {
          const i = d3.interpolate(d.current, d.target);
          return (t) => (d.current = i(t));
        })
        .filter(function (d) {
          return +this.getAttribute("fill-opacity") || arcVisible(d.target);
        })
        .attr("fill", (d) => {
          while (d.depth > 1) d = d.parent;
          return color(d.data.name);
        })
        .attr("fill-opacity", (d) =>
          arcVisible(d.target) ? (d.children ? 0.5 : 1) : 0
        )
        .attr("pointer-events", (d) => (arcVisible(d.target) ? "auto" : "none"))

        .attrTween("d", (d) => () => arc(d.current));

      label
        .filter(function (d) {
          return +this.getAttribute("fill-opacity") || labelVisible(d.target);
        })
        .transition(t)
        .attr("fill-opacity", (d) => +labelVisible(d.target))
        .attrTween("transform", (d) => () => labelTransform(d.current));
    } else {
      // TODO: daj mi modal ovdje otvori bitte marko
    }
  }

  function arcVisible(d) {
    return d.y1 <= 3 && d.y0 >= 1 && d.x1 > d.x0;
  }

  function labelVisible(d) {
    return d.y1 <= 3 && d.y0 >= 1 && (d.y1 - d.y0) * (d.x1 - d.x0) > 0.03;
  }

  function labelTransform(d) {
    const x = (((d.x0 + d.x1) / 2) * 180) / Math.PI;
    const y = ((d.y0 + d.y1) / 2) * radius;
    return `rotate(${x - 90}) translate(${y},0) rotate(${x < 180 ? 0 : 180})`;
  }
}
</script>

<template>
  <div id="dataviz"></div>
</template>
