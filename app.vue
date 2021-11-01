<template>
  <div>
    <component
      :is="item.children ? Group : Link"
      v-for="item in data"
      :key="item.title"
      :item="item"
    />
    <p>It should render all the items defined in data property.</p>
    <p>`deeper` & `3rd level` isn't get rendered because group doesn't recursively call it self.</p>
  </div>
</template>

<script setup>
import Group from "@/app/components/Group.vue";
import Link from "@/app/components/Link.vue";

const data = [
  { title: "Hello" },
  {
    title: "world",
    children: [
      {
        title: "deeper",
        children: [
          {
            title: "3rd level",
          },
        ],
      },
    ],
  },
];
</script>


