<template>
    <section class="main-shop column">
        
        <section class="top-col row">
            <div class="header">Welcome Hello Greetings {{msg}} </div>
        </section>  <!-- End of "top-col column" -->

        <section class="bottom-col row">
            <div class="left-counter">
                <div class="column product column">
                    <div class="p1 row">
                        <button class="product-name"> {{product.name}} </button>
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
    name: 'Store',
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
    background: grey; 
    min-width: 35rem;
    max-width: 60rem;

    padding: 1rem 0 1rem 0;
    border: rgb(202, 202, 202) 7px solid;
}

.top-col {
  padding: 0.5rem;
}
.bottom-col {
    width: 100%;

    border-top: white solid 1px;
}

.left-counter {
    width: 66.66%;

    border-right: white 1px solid;
    padding: 0.5rem; 
}
.right-counter {
    width: 33.33%;
    padding: 0.5rem;
}

.product-name:hover {
  cursor: pointer;
}
</style>