<script setup>
import { ref } from 'vue'
import { useProjectsStore } from '../stores/projectsStore'

const projectsStore = useProjectsStore()
const newProject = ref('')

function addProject() {
  if (!newProject.value) return

  projectsStore.addProject(newProject.value)
  newProject.value = ''
}
</script>

<template>
  <h1>Projects</h1>

  <input v-model="newProject" placeholder="New project" />
  <button @click="addProject">Add</button>

  <ul>
    <li v-for="project in projectsStore.projects" :key="project.id">
      {{ project.name }}
      <button @click="projectsStore.deleteProject(project.id)">
        X      
      </button>
    </li>
  </ul>
</template>