<template>
    <v-container class="px-0" fluid>
        <v-chip v-bind="$attrs" :close-icon="icon" :color="color" @click:close="$emit('close', id)">{{ text }}</v-chip>
    </v-container>
</template>
<script>

export default {
    name: 'Chips',
    
    props: {
        id: {
            type:Number,
            default:0
        },
        text:{
           type: String,
           default: 'Chip' 
        },
        icon: {
            type: String,
            default:'mdi-delete'
        },
        color: {
            type: String,
            default:'green'
        }
    }
};
</script>