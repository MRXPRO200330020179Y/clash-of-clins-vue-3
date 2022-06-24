<template>
    <div class="mb-body">
        <h1>Hello Home</h1>
        
        <div class="card__wrapper" v-for="item in items" :key="item.id">
            <Cart :name="`${item.lvl}`" :title="item.title">
                {{item.descr}}
            </Cart>
        </div>
    </div>
</template>

<script>
import Cart from '@/components/UL/Cart.vue';
export default {
    components:{
        Cart
    },

    data(){
        return{
            items:[
                {
                    id: 1,
                    title:'Archer',
                    descr:'Archer ipsum dolor, sit amet consectetur adipisicing elit. Modi, aut!',
                    lvl:4
                },

                {
                    id: 2,
                    title:'Wizard',
                    descr:'Wizard ipsum dolor, sit amet consectetur adipisicing elit. Modi, aut!',
                    lvl:6
                },
            ]
        }
    }
}
</script>