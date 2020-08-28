<template>
    <div id="grid-images">

        {{ fakeApi }}
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'GridImages',
    data: function() {
        return{
            avatarImg: 'https://avatars3.githubusercontent.com/u/51227200?s=400&v=4',
            usernames: ['AdaBrain', 'Peter Parker', 'Steve Jobs', 'Bill Gates', 'Elon Musk'],
            apis: null,
            fakeApi: null,
        }
    },
    mounted: function() {
        axios
        .get('https://dog.ceo/api/breed/hound/images/random/10')
        .then(response => this.apis = response.data.message)

        axios
        .get('https://api.mocki.io/v1/9caa0ba8')
        .then(response => this.fakeApi = response)        
    }
}
</script>

<style>
    #grid-images {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
    }
</style>