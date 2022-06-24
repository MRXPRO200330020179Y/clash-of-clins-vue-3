<template>
    <div class="mb-body">

        <div class="card__wrapper" v-for="item in items" :key="item.id">
            <Cart 
                :name="`${item.lvl + ' LVL'}`"
                :title="item.title" 
                :imgUrl="item.img" 
                :link="`/${item.alias}`">
                
                {{item.descr}}
            </Cart>
        </div>

    </div>
</template>

<script>
import items from '@/seeders/items.js'

import Cart from '@/components/UL/Cart.vue';
export default {
    components:{
        Cart
    },

    data(){
        return{
            items:items
        }
    }
}
</script>