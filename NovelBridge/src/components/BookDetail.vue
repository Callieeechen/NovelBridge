<template>
    <div class="book-detail">
      <img :src="cover" alt="book.title + ' cover'" class="book-cover" />
      <h2>{{ book.title }}</h2>
      <p>Author: {{ book.author }}</p>
      <span class="genre-badge">{{ book.genre }}</span>
      <div class="book-stats">
        <span class="page-count"><span class="highlighted-number">{{ book.pages }}</span> <span class="text-label">pages</span></span> |
        <span><span class="highlighted-number">{{ book.views }}K</span> <span class="text-label">views</span></span>
      </div>



      <div class="actions">
        <button @click="readBook" class="read-btn">Read</button>
        <button @click="toggleBookmark" class="bookmark-btn">{{ book.isBookmarked ? 'Added' : 'Add to Bookmark' }}</button>
        <button @click="toggleFavourite" class="favourite-btn">
          <img :src="book.isFavourite ? '@/assets/heart-filled.jpg' : '@/assets/heart-unfilled.jpg'" alt="Favourite icon" class="heart-icon" />
        </button>

      </div>
      <div class="book-description">
        <h3>ABOUT</h3>
        <p>{{ book.description }}</p>
      </div>
    </div>

    <div class="book-content">
      <h3>CONTENT . {{ book.chapters.length }} Chapters</h3>
      <div class="chapters-row">
        <div v-for="(chapter, index) in book.chapters" :key="index" class="chapter-title">
          {{ chapter.title }}
        </div>
      </div>
    </div>

  </template>
  
  <script>
  export default {
    props: {
      book: {
        type: Object,
        required: true
      }
    },
    methods: {
      toggleBookmark() {
        this.book.isBookmarked = !this.book.isBookmarked;
        // Further bookmark logic goes here
      },
      toggleFavourite() {
        this.book.isFavourite = !this.book.isFavourite;
        // Further favourite logic goes here
      },
      readBook() {
        // Read book logic goes here
      }
    }
  };
  </script>

  
  <style scoped>
   .book-cover {
    width: 150px; /* Set the width of the image */
    height: auto;
  }

  .book-detail {
    /* Styles to match the book detail container */
  }
  
  .genre-badge {
    /* Styles for the genre badge */
  }
  
  .actions button {
    /* Styles for the action buttons */
  }

  .read-btn {
  background-color: orange; /* Set the background color to orange */
  /* Add any other styling you need for the button, such as padding, border, etc. */
  padding: 5px 20px; /* Example padding */
  border: none; /* Remove border */
  border-radius: 5px; /* Optional: Adds rounded corners to the button */
  margin-right: 10px;
}

.bookmark-btn {
  background-color: white;
  padding: 5px 20px; /* Adjust the padding to change the size */
  border-radius: 5px; /* Example border radius */
  border-color: darkgray;
  margin-right: 10px;
}
 
  
  .book-stats {
    /* Styles for the book stats */
  }

  .highlighted-number {
  font-size: 25px; /* Adjust the font size as needed */
  color: black; /* Ensure the numbers are black */
}

.text-label {
  color: grey; /* Make the text grey */
}

  
  .book-description {
    /* Styles for the book description */
  }

  .heart-icon {
  width: 24px; /* Adjust the size of the heart icon */
  height: 30px;
  margin-right: 5px; /* Space between the icon and the text */
}

chapters-row {
  display: flex; /* Establishes a flex container */
  flex-wrap: wrap; /* Allows items to wrap onto the next line */
  gap: 15px; /* Provides space between items */
  justify-content: flex-start; /* Aligns items to the start of the container */
}



  </style>