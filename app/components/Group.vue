<template>
    <div class="hello">
        <p>Group: {{ item.title }}</p>
        <component
            :is="child.children ? 'Group' : Link"
            v-for="child in item.children"
            :key="child.title"
            :item="child"
        />
    </div>
</template>

<script setup>
import Link from './Link.vue';
defineProps(['item'])
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
