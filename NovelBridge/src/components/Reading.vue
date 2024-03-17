<template>

</template>

<script>

import firebaseApp from '../firebase.js';
import { getFirestore } from 'firebase/firestore';
import { collection, getDocs, doc , deleteDoc } from 'firebase/firestore';
const db = getFirestore(firebaseApp);
let docs = await getDocs(collection(db, 'Books'))

export default {
    data() {
        return {

        }
    }
}

</script>