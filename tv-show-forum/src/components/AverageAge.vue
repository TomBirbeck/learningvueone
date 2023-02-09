<script>
export default {
    props: {
        characters: {
            type: Array,
            required: true,
        }
    },
   computed: {
                averageAgeCalculation(){
                    let ages = []
                    this.characters.map((char)=>{return ages.push(char.age)})
                    let age = ages.reduce((a,b)=>{return a + b}, 0)
                    return age/ages.length
                }
            },
        }
    
</script>

<template>
 <h2>Average Age</h2>
    <p>{{averageAgeCalculation}}</p>
</template>