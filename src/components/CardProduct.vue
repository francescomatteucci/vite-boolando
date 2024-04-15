<template>
    <div class="card product">
                            <div class="card__header">
                                <img class="product__thumb" src="/1.webp" alt="" />
                                <img class="product__thumb thumb--hover" src="./img/1b.webp" alt="" />
                                <span class="btn-heart">&hearts;</span>
                                <ul class="badges">
                                    <li v-for="(badge,i) in product.badges" :key="i" class="badge" :class="`badge--${badge.type}`">{{ badge.value }}</li>
                                </ul>
                            </div>
                            <div class="card__body">
                                <strong class="product__brand">{{ product.brand }}</strong>
                                <h3 class="product__title">{{ product.name }}</h3>
                                <div class="product__price">
                                    <span>{{ product.price }} &euro;</span>
                                </div>
                            </div>
                        </div>
</template>

<script>
    export default{
        props: ['product'],
    }
</script>

<style lang="scss" scoped>

/* CARD PRODUCT */

.card__header img {
    display: block;
}

.card.product .card__header {
    position: relative;
}

.btn-heart {
    width: 40px;
    height: 40px;
    background-color: white;
    font-size: 22px;
    position: absolute;
    top: 20px;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    position: absolute;
    left: 0;
    bottom: 20px;
}

.badge {
    color: white;
    background-color: black;
    font-size: 12px;
    line-height: 30px;
    padding: 0 12px;
    font-weight: bold;
}

.badge.badge--discount {
    background-color: red;
    order: -1;
}

.badge.badge--tag {
    background-color: green;
}

.card__header .product__thumb.thumb--hover {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    transition: opacity 300ms ease-in-out;
}

.card__header .product__thumb {
    aspect-ratio: 1/1;
    width: 100%;
    object-fit: cover;
    object-position: center center;
}

.card:hover .product__thumb.thumb--hover {
    opacity: 1;
}

.product__price :first-child {
    color: red;
    font-weight: 700;
}

.product__price :nth-child(2) {
    color: #555;
}
</style>