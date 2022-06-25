<template>
    <div class="wrapper-person">
        <div v-if="item">
            <img :src="item.img" :alt="item.descr">
            <h1 style="color:#fff;" class="title">{{item.title}}</h1>
            <p>{{item.descr}}</p>

            <div class="card-stats">
                <div v-for="(stat,index) in item.info" :key="index" class="one-third">
                    <div class="stat-value">{{stat.value}}</div>
                    <div class="stat">{{stat.title}}</div>
                </div>
            </div>

            <div>
                <router-link class="btn btnPrimary" to="/">Back to home</router-link>
            </div>
        </div>

        <div v-else>
            <notFund></notFund>
        </div>
    </div>
</template>

<style scoped>
.wrapper-person{
    text-align: center;
}

.btnPrimary{
    background-color: #fff;
    color: rgb(91 52 39);;
    border: none;
}

.card-stats{
    border-radius: 14px;
    background-color: transparent;
    margin: 30px 0;
}
</style>

<script>
import items from '@/seeders/items.js';
import notFund from '@/pages/notFund.vue';
export default {
    data(){
        return{
            item:null
        }
    },

    components:{
        notFund
    },

    created(){
        const alias = this.$route.params.itemAlias
        const item = items.find(el => el.alias === alias)
        this.item = item
        console.log(item)
    }
}
</script>