<template>
    <input v-on="listeners" class="custom-input">
</template>

<script>
    export default {
        name: 'CustomInput',
        computed:{
            listeners(){
                return {
                    ...this.$listeners, 
                    input:event => this.$emit('input', event.target.value)
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
@import '../../assets/scss/variables.scss';

.custom-input{
    max-width: 200px;
  width: 100%;
    min-height: 40px;
    border: 2px solid $main-color;
    font-size: 18px;
    outline: none;
    line-height: inherit;
    padding: 8px 15px;
}
</style>