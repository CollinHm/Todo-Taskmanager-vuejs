<script setup>

</script>

<template>
  <nav>
    <router-link to="/">Today</router-link> |
    <router-link to="/projects">Projects</router-link> |
    <router-link to="/projects/1">Project Detail</router-link> |
    <router-link to="/settings">Settings</router-link>
  </nav>

  <router-view />
</template>