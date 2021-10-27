<template>
    <section class="container">
        <section class="main-shop column">
        
            <section class="top-col row">
                <div class="header">Welcome Hello Greetings {{msg}} </div>
            </section>  <!-- End of "top-col column" -->

            <section class="bottom-col row">
                <div class="left-counter">
                    <div class="column product column">
                        <div class="p1">
                            <h1 class="product-name column" v-for="product in products" :key="product.name" @mouseover="changeToDetail(product.detail)"> {{product.name}}  </h1>
                        </div>
                    </div>
                </div>  <!-- End of "left-counter" -->

                <div class="right-counter">
                    <button class="product-cost column" v-for="product in products" :key="product.cost" v-on:click="addToCart"> {{ product.cost }} coins</button>
                </div>  <!-- End of "right-counter" -->

            </section>  <!-- End of "bottom-col column" -->  
        </section>

        <section class="user">
            <div class="cart">
                <h1>You Bought {{cart}} Items</h1>
            </div>
        </section>
    </section> <!-- End of "container" -->
    
</template>

<script>
export default {
    name: 'Store',
    props: {
        msg:String,
    },
    data (){
        return {
            products: [
                {name:"Bee" , cost: 100, inStock:true, detail: 'A Honey Jar' },
                {name:"Butterfly" , cost: 200, inStock:true,detail: 'Flaky Wings' },
                {name:"Kitty" , cost: 300, inStock:true, detail: 'Mx. Leave Me Alone'},
                {name:"Hardcore" , cost: 400, inStock:true, detail: 'No Hearts'},
                {name:"Hmm" , cost: 500, inStock:true, detail: 'Dunno' },
                
            ], // End of product
            cart: 0,
        } // End of return
    }, // End of data

    methods: {
        addToCart () {
            this.cart += 1
            console.log("done")
        },

        changeToDetail () {
            this.products.name = this.products.detail
            console.log("Completed")
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

.product-name {
    margin: 0;
    padding: 1px 0 ;
    font-weight:100;
}

.product-cost:hover {
  cursor: pointer;
  text-decoration: white 1.5px underline;
}

</style>