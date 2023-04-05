<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>

    <div class="wrapper">
      
      <nav>
        <RouterLink to="/" class="nav-item">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
nav > a{
  display: inline-block;
  padding: 10px;
  margin: 0 2px;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-decoration: none;
  color: #333;
}
</style>