<template>
  <div class="container mt-4">
    <h2>Available Lessons</h2>
    <div class="row">
      <div class="col-md-4 mb-3" v-for="lesson in lessons" :key="lesson.id">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">{{ lesson.topic }}</h5>
            <p class="card-text">
              Location: {{ lesson.location }} <br />
              Price: ${{ lesson.price }} <br />
              Spaces: {{ lesson.spaces }}
            </p>
            <button
              class="btn btn-success"
              :disabled="lesson.spaces === 0"
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
import { cartStore } from "@/store/cartStore";

export default {
  data() {
    return {
      lessons: [],
    };
  },
  methods: {
    async fetchLessons() {
      try {
        const response = await fetch("http://localhost:3000/lessons"); // Replace with your API endpoint
        if (!response.ok) throw new Error("Network response was not ok");
        const data = await response.json();
        this.lessons = data;
      } catch (error) {
        console.error("Error fetching lessons:", error);
      }
    },
    addToCart(lesson) {
      if (lesson.spaces > 0) {
        cartStore.cart.push(lesson);  
        lesson.spaces--;  
        alert(`${lesson.topic} added to cart.`);
      }
    },
  },
  created() {
    this.fetchLessons();
  },
};
</script>
