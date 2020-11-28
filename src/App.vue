<template>

<div id="app">

    @{{user.username}} - {{fullname}}
    <br>
    <strong>Followers:</strong> {{followers}}
    <br>
    <button @click="followUser">
        Follow
    </button>

    <button @click="ResetfollowUser">
        Reset
    </button>

</div>

</template>


<script>

export default {
    name: 'App',
    data(){
        return{
            followers: 0,
            user:{
                id: 1,
                username: '_arik5001',
                firstname: 'Arik',
                lastname: 'Md Isthiaque',
                email: 'arik@isocial.com.bd',
                isAdmin: true
            }
        }
    },
    watch:{
        followers(newfollowersCount, oldfollowersCount){
            if(oldfollowersCount<newfollowersCount){
                console.log(this.user.username+' has gained a follower!')
            }
        }
    },
    computed:{
        fullname(){
            return  this.user.firstname+' '+this.user.lastname
        }
    },
    methods:{
        followUser() {
            this.followers++
        },
        ResetfollowUser(){
            this.followers= 0
        }
    },
    mounted(){
        this.followUser();
    }
}

</script>

<style>

    #app {
    font-family: consolas;
    text-align: center;
    color: info;
    margin-top: 10px;
    }
    
</style>
