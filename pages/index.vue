<template>
    <div>
        <MainBanner></MainBanner>
        <p>
        Index
        </p>
    </div>
</template>
  
<script>
export default {
    
}
</script>

<style lang="scss">
    div{
        p{
            color: black;
        }
    }
    .sectionEx{
        background-color: rgb(136, 83, 83);
        min-height: 50vh;
        &:nth-of-type(1){
            background-color: yellow;
        }
        &:nth-of-type(2){
            background-color: rgb(214, 109, 109);
        }
        &:nth-of-type(3){
            background-color: rgb(0, 0, 0);
        }
        &:nth-of-type(4){
            background-color: rgb(55, 7, 7);
        } 
        &:nth-of-type(5){
            background-color: rgb(111, 0, 0);
        }
    }
</style>