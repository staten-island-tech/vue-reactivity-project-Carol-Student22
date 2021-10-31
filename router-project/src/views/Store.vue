<template>
    <section class="container">
        <section class="main-shop column">
        
            <section class="top-col row">
                <div class="header">Welcome Hello Greetings {{msg}} </div>
            </section>  <!-- End of "top-col column" -->

            <section class="bottom-col row">
                <div class="left-counter">
                    <div class="column product column">
                        <div class="" v-for="product in products" :key="product.name"
                         @mouseover="updateDetail(product.detail) , updateCost(product.cost), updateStock(product.stock)">
                            <btn class="product-name column"> {{product.name}} </btn>
                        </div>
                    </div>
                </div>  <!-- End of "left-counter" -->

                <div class="right-counter column" >
                    <div class="stock"> 
                        
                        
                        <div >
                            <h1 class="right-text"> {{detailDefault}}</h1>
                            <h1 class="right-text"> {{costDefault}} coins</h1>
                        </div>
                    </div>
                </div>  <!-- End of "right-counter" -->


            </section>  <!-- End of "bottom-col column" -->  

            <section class="user">
                <div class="cart">
                    <h1 class="cart-main">You Bought {{cart}} Items</h1>
                    <h2 class="cart-sub">You still have ${{budget}}</h2>

                    <div class="cart-btn row">
                        <button class="btn-buy"  v-on:click="addToCart"  :disabled="stockDefault = 0">Buy</button>
                        <button class="btn-buy">Sell</button>
                    </div>  <!-- End of "cart-btn" -->
                </div>
            </section>
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
            detailDefault: "Hover Over An Object To See The Description",
            stockDefault: 0,
            costDefault:0,
            products: [
                {
                    name:'Honey Soaked Caramel',
                    detail:"Made with the Sweetest Honey. And Caramel.",
                    cost:20,
                    stock: 3,
                },
                {
                    name:'Sugar Sweet Candy Piece',
                    detail:"SUGAR! SUGAR! SUGAR! It's just a candy piece, chill out.",
                    cost:100,
                    stock: 100,
                }
            ],
            cart: 0,
            budget:1000,
        } // End of return
    }, // End of data

    methods: {
        addToCart () {
            this.cart += 1
            console.log("done")
            this.minusQuanity();
        },

        updateDetail (detail) {
            this.detailDefault = detail
            console.log("Updated Deatil")
        },
        updateCost (cost) {
            this.costDefault = cost
            console.log("Updated Cost")
        },
        updateStock(stock) {
            this.stockDefault = stock
        },
        minusQuanity () {

            console.log("hi")
            
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
    width: 50%;

    border-right: gray 2px solid;
    padding: 0.5rem; 
}
.right-counter {
    width: 50%;
    padding: 0.5rem;
}
.user {
    width:100%;
    border-top: 1px solid white ;
}

.right-text {
    margin: 0;
    font-weight: 100;
}

.product-name {
    margin-bottom: 1rem;
}

</style>