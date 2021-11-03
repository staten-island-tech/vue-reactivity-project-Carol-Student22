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
                         v-on:click="updateDetail(product.detail) , updateCost(product.cost), updateStock(product.stock)">
                            <btn class="product-name column"> {{product.name}} </btn>
                        </div>
                    </div>
                </div>  <!-- End of "left-counter" -->

                <div class="right-counter column" >
                    <div class="stock"> 
                        
                        <div >
                            <h1 class="detail"> {{detailDefault}}</h1>
                            <h1 class="cost"> {{costDefault}} coins</h1>
                        </div>
                    </div>
                </div>  <!-- End of "right-counter" -->


            </section>  <!-- End of "bottom-col column" -->  

            <section class="user">
                <div class="cart">
                    <h1 class="cart-text cart-main">You Bought {{cart}} Items</h1>
                    <h2 class="cart-text cart-sub">You still have ${{budget}}</h2>

                    <div class="cart-btn row">
                        <button :disabled="stockDefault <= 0 ||  budget <= 0 || budget < costDefault" :class="{disabled: stockDefault <= 0 ||  budget <= 0 || budget < costDefault }" class="btn-buy"  v-on:click="addToCart(), minusBudget()">Buy</button>
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
                    detail:"Post-Charred Sugar Soaked in Bee Vomit",
                    cost:20,
                    stock: 3,
                },
                {
                    name:'Sugar Candy Piece',
                    detail:"SUGAR! SUGAR! SUGAR! No Clue What A Candy Piece Is",
                    cost:10,
                    stock: 100,
                },
                {
                    name:'Pastry Disk',
                    detail:"A disk shaped pastry.",
                    cost:15,
                    stock: 8,
                },
                {
                    name:'Tumble Weed Candy',
                    detail:"It Ain't Weed. It's Tumble Dried.",
                    cost:25,
                    stock: 1,
                },
                {
                    name:`Jack O' Late`,
                    detail:"The Pumpkin's Late For It's Carving Date",
                    cost:200,
                    stock: 0,
                },
                {
                    name:`Candle`,
                    detail:"It's A Candle. Don't Overthink This. ",
                    cost:1,
                    stock: 10,
                },
                {
                    name:'Overthought Candle',
                    detail:"A Thought A Day Keeps The Candles A Flame",
                    cost:1,
                    stock: 10,
                },
                {
                    name:'Timber Log',
                    detail:"Oi Don't Come At Me About The Prices. Natural Resources Are Expensive.",
                    cost:50,
                    stock: 3,
                },
                {
                    name:':)',
                    detail:":D",
                    cost:1001,
                    stock: 5,
                },
            ],
            cart: 0,
            budget:1000,
        } // End of return
    }, // End of data

    methods: {
        addToCart () {
            this.cart += 1
            console.log("Added to Cart")
            this.minusQuanity();
        },

        updateDetail (detail) {
            this.detailDefault = detail
            console.log("Updated Deatil")
        },
        updateCost (cost) {
            this.costDefault = cost
            console.log(cost)
        },
        updateStock(stock) {
            this.stockDefault = stock
        },
        minusQuanity () {
            console.log("Original Stock:" + this.stockDefault)
            this.stockDefault = this.stockDefault - 1
            console.log ("New Stock:" + this.stockDefault)
        },
        minusBudget () {
            console.log("Original Budget:" + this.budget)
            this.budget = this.budget - this.costDefault
            console.log ("New Stock:" + this.budget)
        }

    }
} 
</script>

<style scoped>
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
    margin-bottom: 1rem;
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
    border-top: 1px solid white ;}

.cost {
    margin-top: 1rem;
}
.product-name {
    margin-bottom: 1rem;
}
.btn-buy:hover {
    cursor: pointer;
}
.btn-buy{
    margin-top: 1rem;
    padding: 5px 0.5rem;
    border: 1px solid white;
    color: white;
}
.cart-text{
    margin-top: 0.5rem ;
}

.disabled {
    border: 1px solid rgb(53, 53, 53);
    color: grey;
}
</style>