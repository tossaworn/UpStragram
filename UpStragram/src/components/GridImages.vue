<template>
    <div id="grid-images">
        <div class="ui card" v-for="(username, i) in usernames" :key=i>
            <div class="content">
                <div class="right floated meta">14h</div>
                <img class="ui avatar image" :src="avatarImg">
                <b>{{ username }}</b>
            </div>
            <div class="image">
                <img :src="avatarImg">
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
    </div>
</template>

<script>
export default {
    name: 'GridImages',
    data: function() {
        return{
            avatarImg: 'https://avatars3.githubusercontent.com/u/51227200?s=400&v=4',
            usernames: ['AdaBrain', 'Peter']
        }
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