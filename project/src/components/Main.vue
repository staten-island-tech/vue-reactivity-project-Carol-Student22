<template>
    <section class="main-shop column">
        
        <section class="top-col row">
            <div class="header">Welcome Hello Greetings {{msg}} </div>
        </section>  <!-- End of "top-col column" -->

        <section class="bottom-col row">
            <div class="left-counter">
                <div class="column product column">
                    <div class="p1 row">
                        <button class="name"> {{product.name}} </button>
                    </div>
                </div>
            </div>  <!-- End of "left-counter" -->

            <div class="right-counter">
                <button class="cost"> {{ product.cost }} </button>
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

    padding: 1rem 0 1rem 0;
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