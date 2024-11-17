<template>
    <div class="container mt-4">
      <h2>Available Lessons</h2>
      <div class="row">
        <div class="col-md-4 mb-3" v-for="lesson in lessons" :key="lesson.id">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">{{ lesson.subject }}</h5>
              <p class="card-text">
                Location: {{ lesson.location }} <br />
                Price: ${{ lesson.price }} <br />
                Spaces: {{ lesson.space }}
              </p>
              <button
                class="btn btn-success"
                :disabled="lesson.space === 0"
                @click="addToCart(lesson)"
              >
                Add to Cart
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        lessons: [
          { id: 1, subject: "Math", location: "Hendon", price: 100, space: 5 },
          { id: 2, subject: "Science", location: "Colindale", price: 80, space: 0 },
          { id: 3, subject: "History", location: "Brent Cross", price: 90, space: 3 },
        ],
      };
    },
    methods: {
      addToCart(lesson) {
        if (lesson.space > 0) {
          lesson.space--;
          alert(`${lesson.subject} added to cart.`);
        }
      },
    },
  };
  </script>
  