<template>
   <div class="result">
        <div class="title">{{ results[resultIndex].title }}</div>
        <div class="desc">
            {{ results[resultIndex].desc }}
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Result',
        props:['results','totalCorrect'],
        computed:{
            // this function below will only run if the totalCorrect or the results update, saving performance & time
            resultIndex(){
                let i = 0;
                this.results.forEach((element, index) => {
                    if(element.min <= this.totalCorrect && element.max >= this.totalCorrect){
                        i = index;
                    }
                });
                return i;
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>