<template>
    <div class="container">
        <ul class=" logos-ul">
            <li v-for="car in logos" class="logos-li">
                <img :src="car.src" @click="click(car)">
            </li>
        </ul>
    </div>
</template>

<script>
    import {logos} from '@/utils/data'

    console.log('logos:')
    console.log(logos)

    export default {
        components: {},
        data () {
            return {
                logos: logos
            }
        },
        created () {

        },
        methods: {
            click () {

            }
        }
    }
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        box-sizing: border-box;
    }
    .logos-ul {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .logos-li{
        width:33%;
    }
</style>
