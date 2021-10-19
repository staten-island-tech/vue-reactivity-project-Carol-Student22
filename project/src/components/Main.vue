<template>
    <section class="main-shop column">
        
        <section class="top-col row">
            <div class="header">Welcome Hello Greetings {{msg}} </div>
        </section>  <!-- End of "top-col column" -->

        <section class="bottom-col row">
            <div class="left-counter">
                <div class="column product column">
                    <div class="p1 row">
                        <h2 class="name"> {{product.name}} </h2>
                        <button class="cost"> {{ product.cost }} </button>
                    </div>
                </div>
            </div>  <!-- End of "left-counter" -->

            <div class="right-counter">
                <h1>dd</h1>
            </div>  <!-- End of "right-counter" -->

        </section>  <!-- End of "bottom-col column" -->

    </section>
</template>

<script>
export default {
    name: 'Main',
    props: {
        msg:String,
    },
    data (){
        return {
            product: {
                name:"Bee" , cost: 100,
            } // End of product
        } // End of return
    } // End of data
} 
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
* {
    font-family: 'VT323', monospace;
    font-size: 1.5rem;
}

.row {
    display: flex;
    flex-direction: row;
}

.column {
    display: flex;
    flex-direction: column;
}

.main-shop {
    background: rgb(148, 144, 144); 
    min-width: 35rem;
    max-width: 70rem;

    padding: 2rem;
    border: rgb(202, 202, 202) 7px solid;
}

.bottom-col {
    width: 100%;
    background: rgb(82, 67, 67);
}

.left-counter {
    background: rgb(80, 34, 34);
    width: 100%;
}
.right-counter {
    background: rgb(185, 73, 73);
    width: 50%;

}

</style>