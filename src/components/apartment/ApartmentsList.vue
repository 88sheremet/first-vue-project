<template>
    <PageContainer>
        <div class="apartments-list">
<ApartmentItem v-for="apartment in items" 
:key="apartment.id" 
:descr="apartment.descr" 
:rating="apartment.rating" 
:imgSrc="apartment.imgUrl" 
:price="apartment.price" 
class="apartments-list__item"/>
    </div>
    </PageContainer>
</template>

<script>
import ApartmentItem from './ApartmentItem.vue';
import PageContainer from '../shared/Container.vue'
    export default {
        name:"ApartmentsList",
        props:{
            items:{
                type:Array,
                default: ()=>[],
            }
        },
        components:{
            ApartmentItem,
            PageContainer,
        }
    }
</script>

<style lang="scss" scoped>
.apartments-list{
    display: flex;
    flex-wrap: wrap;
    margin-left: -15px;
    margin-right: -15px;

    &__item{
        margin-bottom: 30px;
    }
}
</style>