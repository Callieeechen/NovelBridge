<template>
    <div class="library">
      <div class="book-list">
        <div class="book-card" v-for="book in books" :key="book.id">
          <img :src="book.cover" alt="Book cover" class="book-cover">
          <div class="book-details">
            <h2 class="book-title">{{ book.title }}</h2>
            <p class="book-author">Author: {{ book.author }}</p>
            <p class="book-category">Category: {{ book.category }}</p>
            <p class="book-pages">{{ book.pages }} Pages</p>
            <p class="book-preview">preview preview preview preview ...</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        books: [
          // Populate this array with your books data
          {
            id: 1,
            title: 'The Kamogawa Food Detectives',
            author: 'Hishashi Kashiwai',
            category: 'Mystery',
            pages: '159',
            cover: 'path-to-kamogawa-food-detectives-cover.jpg'
          },
          // ... other book objects
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .library {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 20px;
    background-color: #f1f1f1;
  }
  
  .book-list {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  
  .book-card {
    width: 180px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    border-radius: 10px;
    overflow: hidden;
    background-color: #fff;
  }
  
  .book-cover {
    width: 100%;
    display: block; /* Removes bottom space under the image */
  }
  
  .book-details {
    padding: 10px;
  }
  
  .book-title {
    font-size: 16px;
    font-weight: 600;
    color: #333;
  }
  
  .book-author,
  .book-category,
  .book-pages,
  .book-preview {
    font-size: 14px;
    color: #666;
  }
  </style>
  