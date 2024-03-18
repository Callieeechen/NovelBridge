<template>
    <div id="header_pane"> 
        <!-- for the previous and next button -->

    </div>

    <div id="left_pane">
        <!-- for advertizing -->
    </div>

    <div id="reading pane">
        {{ chapter_data }}
    </div>

    <div id="right_pane">
        <!-- for utility buttons -->
    </div>

    <div id="footer pane">
        <!-- for the previous and next button -->

    </div>

</template>

<script>

import firebaseApp from '../firebase.js';
import { getFirestore } from 'firebase/firestore';
import { collection, getDocs, doc , deleteDoc } from 'firebase/firestore';



export default {
    props: ['bookName'],
    created() {
        async function getChapters(bookN) {
            const db = getFirestore(firebaseApp);
            const book = await getDocs(collection(db, 'Books',bookN))
            let chapters = book.data().Chapters 
            return chapters

        }
    },
    mounted() {
        function goToNextChapter(){
            for (let i=0;i<len(keys)-1;i++){
                if chapter == keys[i] {
                    chapter = keys[i+1]
                    chapter_data = all_chapters[chapter]
                }
            }
        }
        function goToPreviousChapter(){
            for (let i=1;i<len(keys);i++){
                if chapter == keys[i] {
                    chapter = keys[i-1]
                    chapter_data = all_chapters[chapter]
                }
            }
        }
    }
    data() {
        return {
            all_chapters = getChapters(bookName)
            keys = all_chapters.getKeys()
            chapter = keys[0]
            chapter_data = all_chapters[chapter]
        }
    }
}

</script>