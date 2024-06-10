<template>
    <div class="header">
        <div class="buttons">
            <button @click="$router.push('/')" class="button is-primary is-outlined is-rounded">HOME</button>
            <button @click="$router.push('/works')" class="button is-primary is-outlined is-rounded">WORKS</button>
            <button  class="button is-primary is-outlined is-rounded"><a href="https://github.com/matoi0317">GitHub</a></button>
        </div>
    </div>
</template>

<script>
export default {
  name: 'GlobalHeader'
}
</script>

<style scoped lang="scss">
.header {
    width: 100%;
    height: 20%;
    display: flex;
    justify-content: flex-end;  
    box-shadow: 0 4px 4px 0 rgba(160, 160, 160, 0.2);
    .buttons {
        width: 50%;
        margin: 20px;
    display: flex;
    justify-content: flex-end;
    a {
        color: #03D1B2;
    }
        button {
            // margin: 20px;
            margin: 0 20px 0 0;
        }
    }
}
</style>