<script>

export default {
    name: "SingleMovie",
    data: function () {
        return {
         
        };
    },
    methods: {
        
    },
    props: {
        "Movie": Object
    }
}
</script>


<template>
    <div>
        {{ Movie.title }}

    </div>
</template>


<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;


</style>

