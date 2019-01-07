<template>
    <div class="key-wizard">
        <key v-if="needsPressed.length === 0">Enter</key>
        <key v-for="key in needsPressed" :key="key">{{ key }}</key>
    </div>
</template>

<script>
import key from './key.vue'
export default {
    components: {
        key
    },
    props: {
        needsPressed: {
    
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
.key-wizard{
    display: flex;
}
</style>
