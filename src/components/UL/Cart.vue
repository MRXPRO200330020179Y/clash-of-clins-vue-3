<template>
    <div class="card">
        <div v-if="imgUrl" class="card-img__wrapper">
            <img class="card-img" :src="imgUrl" alt="title">
        </div>
        <span class="card-name">{{name}}</span>
        <span class="card-title">{{title}}</span>
        <div class="card-bady">
           <slot>{{item.descr}}</slot>
        <router-link 
            v-if="link" 
            class="link" 
            :to="link"
            style="display: block; margin-top: 16px; margin-bottom: 16px;">
            See more
        </router-link>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        name:{
            type:String,
            required:true,
        },

        title:{
            type:String,
            required:true,
        },

        imgUrl:{
            type:String,
        },

        link:{
            type:String,
        }
    }
}
</script>