<template>
    <div class="key">
        <slot></slot>
    </div>
</template>

<script>
export default {
    props: {

    },
    data(){
        return{
            input: ''
        }
    }
}
</script>

<style lang="scss" scoped>
.key{
    border:1px solid gray;
    font-size:1.2em;
    box-shadow:1px 0 1px 0 #eee, 0 2px 0 2px #ccc, 0 2px 0 3px #444;
    -webkit-border-radius:3px;
    -moz-border-radius:3px;
    border-radius:3px;
    margin:2px 6px;
    padding:1px 5px;
}
</style>
