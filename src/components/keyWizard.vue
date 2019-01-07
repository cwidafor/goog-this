<template>
    <div class="key-wizard">
        <key v-if="needsPressed.length === 0">Enter</key>
        <key v-for="(key,index) in needsPressed" 
            :key="index">
            <span v-if="key === ' '">Space</span>
            <span v-else>{{ key }}</span>
        </key>
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
    margin-top: 2rem;
    display: flex;
}
</style>
