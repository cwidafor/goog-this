<template>
    <div class="smart-input">
        <input type="text" v-model="input">
        <p>{{ goal }}</p>
    </div>
</template>

<script>
export default {
    watch: {
        input: {
            handler: function(newIsh){
                this.$emit('inputEvent', newIsh);
            }
        }
    },
    props: {
        goal: {
            type: String,
            required: true
        }
    },
    data(){
        return{
            input: ''
        }
    }
}
</script>

<style lang="scss" scoped>
.smart-input{
    background: #fff;
    display: flex;
    border-radius: 2px;
    border: none;
    box-shadow: 0 2px 2px 0 rgba(0,0,0,0.16), 0 0 0 1px rgba(0,0,0,0.08);
    z-index: 3;
    height: 44px;
    margin: 1.5rem auto;
    width: 36rem;
    position: relative;
}
input{
    background-color: transparent;
    border: none;
    margin: 0;
    padding: 0.25rem 1rem;
    color: rgba(0,0,0,.87);
    word-wrap: break-word;
    outline: none;
    -webkit-tap-highlight-color: transparent;
    font: 16px arial,sans-serif;
    line-height: 34px;
    height: 34px !important;
    width: 100%;
}
p{
    background-color: transparent;
    border: none;
    margin: 0;
    padding: 0.25rem 1rem;
    color: rgba(0,0,0,.2);
    -webkit-tap-highlight-color: transparent;
    font: 16px arial,sans-serif;
    line-height: 34px;
    height: 34px !important;
    width: 100%;
    position: absolute
}
</style>
