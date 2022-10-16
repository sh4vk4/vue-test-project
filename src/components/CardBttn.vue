<!-- шаблон для кнопок внутри карточек -->
<template>
    <!-- при нажатии на кнопку вызывается событие buy -->
    <div class="bttn" @click="buy">
        <!-- если кнопка нажата и грузится - показывается лоудер -->
        <div v-if="loading" class="lds-dual-ring"></div>
        <!-- при не нажатой кнопке - показывается текст купить, при нажатой - что картина в корзине -->
        <button v-if="!loading" v-bind:class="{'': !clicked, 'active': clicked}">
            <span v-if="!clicked">Купить</span>
            <span v-if="clicked"><img src="@/assets/check.svg" alt=""> В корзине</span></button>
    </div>
</template>

<!-- создание событий при нажатии кнопки купить -->
<script>
export default {
    data() {
        return {
            loading: false,
            clicked: false
        };
    },
    methods: {
        buy() {
            this.loading = !false
            this.clicked = !false
            setTimeout(() => {
                this.loading = !true
            }, 2000)
        }
    }
}
</script>

<style>
/* стиль для нажатой кнопки */
.active {
    background-color: #5B3A32;
    cursor: default;
}

.active img {
    cursor: default;
}

.active span {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: .25rem;
}

.active:hover {
    background-color: #5B3A32;
}

/* лоудер */
.lds-dual-ring {
    transform: scale(.35);
    display: inline-block;
    width: 46px;
    height: 46px;
}

.lds-dual-ring:after {
    content: " ";
    display: block;
    width: 64px;
    height: 64px;
    margin: 8px;
    border-radius: 50%;
    border: 8px solid #343030;
    border-color: #343030 transparent #343030 transparent;
    animation: lds-dual-ring .8s linear infinite;
}

/* анимация лоудера */
@keyframes lds-dual-ring {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }
}
</style>