<template>
    <div class="products-section">
        <h2>NEW PRODUCTS</h2>
        <p>Choose the headset that best suits your needs. We offer top-quality options with a variety of features to enhance your audio experience</p>
        <div class="product-list">
            <div class="product-card" v-for="(product, index) in products" :key="index">
                <img 
                    :src="product.src" 
                    alt="Headset" 
                    class="product-image" 
                    @mouseover="hoverImage(index)" 
                    @mouseout="resetImage(index)"
                >
                <p>{{ product.description }}</p>
                <div class="price">
                    {{ product.price }}
                    <span class="original-price">{{ product.originalPrice }}</span>
                </div>
                <button>ADD TO CART<i class="bi bi-cart3"></i></button>
            </div>
        </div>
    </div>
</template>

<script>
import image1 from '@/assets/img/1.svg';
import image2 from '@/assets/img/2.svg';

export default {
    data() {
        return {
            products: [
                {
                    src: image1,
                    hoverSrc: image2,
                    description: 'Gabini® K-29 Premium Headset with Multi-Device Connectivity and Noise-Canceling Technology, Black.',
                    price: '$94.99',
                    originalPrice: '$139.99'
                },
                {
                    src: image1,
                    hoverSrc: image2,
                    description: 'Gabini® K-29 Premium Headset with Multi-Device Connectivity and Noise-Canceling Technology, Black.',
                    price: '$94.99',
                    originalPrice: '$139.99'
                },
                {
                    src: image1,
                    hoverSrc: image2,
                    description: 'Gabini® K-29 Premium Headset with Multi-Device Connectivity and Noise-Canceling Technology, Black.',
                    price: '$94.99',
                    originalPrice: '$139.99'
                }
            ]
        }
    },
    methods: {
        hoverImage(index) {
            this.products[index].src = this.products[index].hoverSrc;
        },
        resetImage(index) {
            this.products[index].src = image1;
        }
    }
}
</script>

<style scoped>
.products-section {
    text-align: center;
    min-height: 100vh; 
    background-color: #f7f7f7;
    border: 1px solid #ddd; 
    border-radius: 25px;
    padding: 40px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1); 
}

.products-section h2 {
    font-size: 28px;
    margin-bottom: 10px;
    font-weight: 700;
}

.products-section p {
    color: #666;
    margin-bottom: 30px;
    max-width: 600px;
    margin: 0 auto;
}

.product-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap; 
    gap: 20px;
}

.product-card {
    background-color: transparent;
    border-radius: 10px;
    padding: 20px;
    width: 250px;
    text-align: center;
    overflow: hidden;
}

.product-card img {
    width: 100%;
    transform: scale(3);
    transform-origin: center;
    margin-bottom: 50px;
    margin-top: 50px;
}

.product-card h3 {
    font-size: 18px;
    margin: 10px 0;
}

.product-card .price {
    font-size: 24px;
    color: #333;
    margin-bottom: 10px;
    position: relative;
    display: inline-block;
    font-weight: 700;
}

.product-card .price::before {
    content: '$';
    font-size: 14px;
    position: relative;
    top: -10px;
    margin-right: 2px;
}

.product-card .original-price {
    font-size: 12px;
    text-decoration: line-through;
    color: #ff0000;
    position: relative;
    margin-left: 5px;
    top: -10px;
}

.product-card button {
    background-color: #fff;
    color: #000;
    border: 1px solid #b9b9b9;
    border-radius: 30px;
    padding: 8px 10px;
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    width: auto;
    max-width: none;
    margin: 0 auto;
    cursor: pointer;
    position: relative;
    transition: border-color 0.3s ease;
}

.product-card button:hover {
    border-color: #000;
}

.product-card button i {
    background-color: #000;
    color: #fff;
    border-radius: 50%;
    padding: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-left: 20px;
}


@media (max-width: 768px) {
    .product-list {
        flex-direction: column;
        align-items: center;
    }
}
</style>