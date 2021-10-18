<template>
    <section class="main-shop">
        <div class="header">Welcome Hello Greetings {{msg}} </div>

        <div class="row counter">
            <h1 class="text"></h1>
            <div class="column product">
                <button class="btn"></button>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Main',
    props: {
        msg:String,
    }
}
</script>

<style >
.main-shop {
    
}
</style>