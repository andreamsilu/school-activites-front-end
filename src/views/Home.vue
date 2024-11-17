<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <!-- Navigation Bar -->
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">School Activities</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarNav"
            aria-controls="navbarNav"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
              <li class="nav-item">
                <router-link to="/" class="nav-link active">Home</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/cart" class="nav-link">Cart</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/checkout" class="nav-link">Checkout</router-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
  
      <!-- Welcome Section -->
      <div class="jumbotron text-center mt-4">
        <h1 class="display-4">Welcome to School Activities!</h1>
        <p class="lead">
          Browse and book after-school classes and activities for students and parents.
        </p>
        <router-link to="/" class="btn btn-primary btn-lg">View Lessons</router-link>
      </div>
  
      <!-- Lesson List Component -->
      <LessonList />
    </div>
  </template>
  
  <script>
  import LessonList from "../components/LessonList.vue";
  
  export default {
    components: {
      LessonList,
    },
  };
  </script>
  
  <style scoped>
  .jumbotron {
    background-color: #f8f9fa;
    padding: 2rem 1rem;
    margin-bottom: 2rem;
  }
  </style>
  