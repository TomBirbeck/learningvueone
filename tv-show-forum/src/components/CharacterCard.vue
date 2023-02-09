<script>
export default {
    props: {
        character: {
            type: Object,
            required: true
        }
    },
    emits: ['favourite'],
    methods: {
        favouriteCharacter() {
            this.$emit('favourite', this.character);
        },
    }
}
</script>

<template>
    <div>
       <p>{{character.name}}</p>
       <button v-on:click="favouriteCharacter">select as favourite</button>
    </div>
</template>