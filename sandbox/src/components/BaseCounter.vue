<script>
export default {
    data: () => ({
        count: 10,
        counterTitle: 'Counter Standard',
        incrementAmount : 8,
    }),
    computed: {
                displayTitle(){
                    if (this.count > 20) {
                        return 'Counter Standard - Very Long'
                    } else {
                        return 'Counter Standard'
                    }
                },
                optimisedIncrementAmount() {
                    return this.displayTitle.length * this.incrementAmount
                }
            },
            methods: {
                incrementCount(){
                    this.count += this.optimisedIncrementAmount
                }
            },
}
</script>

<template>
      <h1>{{displayTitle}}</h1>
        <p>{{count}}</p>
        <button v-on:click="incrementCount">increment count</button>
        <div>
            <label for="incrementAmount">Increment by:</label>
            <input type="number"
            v-model="incrementAmount"
             />
        </div>
        <p>{{incrementAmount}}</p>
        <p>{{optimisedIncrementAmount}}</p>
</template>