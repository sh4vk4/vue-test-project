<!-- шаблон для карточек с картинами -->
<template>
    <!-- подключение массива к диву + если карточка отключена - добавить ей класс disable -->
    <div id="carditem" v-bind:class="{disable: card.disable}" v-for="card in cardinfo" class="carditem">
        <div class="carditem-image">
            <!-- картина -->
            <img :src="require(`../assets/paintings/${card.img}.jpg`)">
        </div>
        <div class="carditem-text">
            <!-- заголовок с названием картины и автором -->
            <h2>{{card.title}}</h2>
            <div class="carditem-text-info">
                <div class="price">
                    <!-- скидка -->
                    <h6>{{card.discount}}</h6>
                    <!-- цена -->
                    <h3>{{card.price}}</h3>
                </div>
                <!-- вставленый шаблон кнопок -->
                <CardBttn />
            </div>
        </div>
    </div>
</template>

<!-- импортирование шаблона кнопок и создание массива ланных -->
<script>
import CardBttn from '@/components/CardBttn'

export default {
    components: { CardBttn },
    data() {
        return {
            cardinfo: [
                { img: 'card-1', title: '«Рождение Венеры» Сандро Боттичелли', price: '1 000 000 $', discount: '2 000 000 $', disable: false, cart: false },
                { img: 'card-2', title: '«Тайная вечеря» Леонардо да Винчи', price: '3 000 000 $', discount: '', disable: false, cart: false },
                { img: 'card-3', title: '«Сотворение Адама» Микеланджело', price: '5 000 000 $', discount: '6 000 000 $', disable: false, cart: false },
                { img: 'card-4', title: '«Урок анатомии» Рембрандт', price: 'Продана на аукционе', discount: '', disable: true, cart: false },
            ]
        }
    }
}
</script>

<style scoped>
/* стиль для заголовков - скидки и цены */
h2 {
    cursor: pointer;
}

h6 {
    text-decoration: line-through;
    color: #A0A0A0;
}

/* стиль для карточек */
.carditem {
    display: flex;
    flex-direction: column;
    border: 1px solid #E1E1E1;
    transition: .5s ease-in-out;
}

/* стиль для картины внутри карточки */
.carditem-image {
    border-bottom: 1px solid #E1E1E1;
    height: 10rem;
    background-position: center;
    background-size: cover;
    cursor: pointer;
    overflow: hidden;
    display: flex;
    align-items: flex-start;
    justify-content: center;
}

img {
    width: 130%;
}

/* стиль для скидки и цены */
.carditem-text {
    display: flex;
    flex-direction: column;
    padding: 1.25rem 1.5rem;
    gap: 1.75rem;
}

.carditem-text-info {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* стиль для "выключенной" карточки */
.disable {
    opacity: .5;
}

.disable .bttn {
    display: none;
}
</style>