<template>
    <div class="mb-body">

        <carousel :settings="settings" :breakpoints="breakpoints">
    

        <slide class="card__wrapper" v-for="item in items" :key="item.id">
            <Cart 
                :name="`${item.lvl + ' LVL'}`"
                :title="item.title" 
                :imgUrl="item.img" 
                :link="`/${item.alias}`">

                <template v-slot:body>
                   {{item.descr}}
                </template>

                <template v-slot:footer>
                   <div class="card-stats">
                     <div v-for="(stat,index) in item.info" :key="index" class="one-third">
                        <div class="stat-value">{{stat.value}}</div>
                        <div class="stat">{{stat.title}}</div>
                     </div>
                   </div>
                </template>
            </Cart>
        </slide>


            <template #addons>
                <navigation />
            </template>
        </carousel>
    </div>
</template>

<script>
import items from '@/seeders/items.js';

import 'vue3-carousel/dist/carousel.css';

import Cart from '@/components/UL/Cart.vue';

import { Carousel, Slide, Navigation } from 'vue3-carousel';

export default {
    components:{
        Cart,
        Carousel,
        Slide,
        Navigation,
    },

    data(){
        return{
            items:items,

            // carusel
            settings:{
                  itemsToShow:3,
                  wrapAround:true,
                  snapAlign: 'center',
            },

            breakpoints:{ 
                1050:{
                    itemsToShow:3,
                },

                700:{
                    itemsToShow:2,
                },

                300:{
                    itemsToShow:1,
                },

                200:{
                    itemsToShow:1,
                },
            }
        }
    }
}
</script>