<template>
    <section class="main-shop column">
        
        <section class="top-col row">
            <div class="header">Welcome Hello Greetings {{msg}} </div>
        </section>  <!-- End of "top-col column" -->

        <section class="bottom-col row">
            <div class="left-counter">
                <div class="column product column">
                    <div class="p1">
                        <button class="product-name column" v-on:click="generateDescription" v-for="product in products" :key="product.name"> {{product.name}} </button>
                    </div>
                </div>
            </div>  <!-- End of "left-counter" -->

            <div class="right-counter">
                <button class="product-cost column" v-for="product in products" :key="product.cost" > {{ product.cost }} coins</button>
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
            userBank:{},
            products: [
                {name:"Bee" , cost: 100, description: "h",},
                {name:"Butterfly" , cost: 200, description: "g",},
                {name:"Kitty" , cost: 300, description: "f",},
                {name:"Hardcore" , cost: 400, description: "d",},
                {name:"Hmm" , cost: 500, description: "s",},
                
            ] // End of product
        } // End of return
    }, // End of data

    methods: {
        generateDescription: function () {

            console.log("done")
            this.product= [];
            this.products.push(this.product);
        }


    }
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
    min-width: 35rem;
    max-width: 60rem;

    border: rgb(202, 202, 202) 3px solid;
    margin: 2rem 0 0 0 ;
}

.top-col {
  padding: 0.5rem;
}
.bottom-col {
    width: 100%;

    border-top: white solid 2px;
}

.left-counter {
    width: 66.66%;

    border-right: gray 2px solid;
    padding: 0.5rem; 
}
.right-counter {
    width: 33.33%;
    padding: 0.5rem;
}

.product-cost,
.product-name {
    border: none;
}

.product-cost:hover,
.product-name:hover {
  cursor: pointer;
  
  text-decoration: white 1.5px underline;
}
</style>