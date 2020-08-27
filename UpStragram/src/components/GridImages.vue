<template>
    <div id="grid-images">
        <div class="ui card" v-for="(username, i) in usernames" :key=i>
            <div class="content">
                <div class="right floated meta">14h</div>
                <img class="ui avatar image" :src="avatarImg">
                <b>{{ username }}</b>
            </div>
            <div class="image">
                <img :src="apis[i]">
            </div>
            <div class="content">
                <span class="right floated">
                <i class="heart outline like icon"></i>
                17 likes
                </span>
                <i class="comment icon"></i>
                3 comments
            </div>
            <div class="extra content">
                <div class="ui large transparent left icon input">
                    <i class="heart outline icon"></i>
                    <input type="text" placeholder="Add Comment...">
                </div>
            </div>
        </div>
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