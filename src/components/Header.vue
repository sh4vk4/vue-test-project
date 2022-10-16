<!-- шаблон шапки -->
<template>
  <header id="header" class="container">
    <!-- меню-бургер, при нажатии на который открывается моб. меню -->
    <img @click="open" src="@/assets/menu.svg">
    <!-- мобильное меню -->
    <div v-bind:class="{'closed': menuClose, 'opened': menuOpen}" class="mobile">
      <img @click="close" src="@/assets/close.svg" alt="">
      <!-- список ссылок, выводимых в моб. меню -->
      <ul>
        <li>
          Каталог
        </li>
        <li>
          Доставка
        </li>
        <li>
          Оплата
        </li>
        <li>
          Контакты
        </li>
        <li>
          О компании
        </li>
      </ul>
    </div>
    <!-- шаблон обычных ссылок -->
    <MenuList/>
    <!-- форма поиска по картинам -->
    <form>
      <input v-model="search" placeholder="Поиск по названию картины" type="search" name="" id="">
      <button>Найти</button>
    </form>
  </header>
</template>

<!-- импортирование шаблонов, создание событий открытия и закрытия моб. меню, поиска по картинам -->
<script>
import MenuList from '@/components/MenuList';
import CardItem from '@/components/CardItem'


export default {
  name: 'header',
  components: {
    MenuList,
    CardItem
  },
  data() {
    return {
      search: '',
      menuOpen: false,
      menuClose: true
    };
  },
  methods: {
    open() {
      this.menuOpen = !false
      this.menuClose = !true
    },
    close() {
      this.menuOpen = !false
      this.menuClose = true
    }
  }
}
</script>

<style>
/* viewport'ы */
@media screen and (max-width: 800px) {
  form {
    width: 100%;
  }

  input {
    width: 100%;
  }
}

@media screen and (min-width: 1549px) {

  header{
    display: flex;
    justify-content: space-between;
  }

  header img {
    display: none;
  }

}

/* стиль для открытого и закрытого моб. меню */
.opened {
  transition: all .3s ease-in-out;
  left: 0;
}

.closed {
  transition: all .3s ease-in-out;
  left: -170rem;
}

/* стиль моб. меню */
.mobile {
  z-index: 10;
  padding: 3rem 1rem;
  position: absolute;
  top:0;
  width: 100vw;
  height: 100vh;
  background-color: #F6F3F3;
  box-shadow: .25rem 0 1.5rem rgba(0, 0, 0, 0.35);
}

/* стиль для закрытия меню  */
.mobile img {
  position: absolute;
}

/* список ссылок в моб. меню */
.mobile ul {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2.5rem;
}

/* стиль для шапки */
header {
  gap: 2rem;
}

/* стиль для изображений внутри шапки */
img {
  cursor: pointer;
}

/* стиль для формы */
form {
  display: flex;
}

/* стиль для поля ввода */
input {
  font-family: 'Merriweather', serif;
  font-size: 14px;
  font-weight: 400;
  color: #343030;
  padding: 0 1rem;
  border-radius: 0%;
  border: 1px solid #E1E1E1;
  background-color: transparent;
}

input:placeholder-shown {
  text-overflow: ellipsis;
}

input:focus {
  outline: none;
}

input[type="search"]::-webkit-search-decoration,
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-results-button,
input[type="search"]::-webkit-search-results-decoration {
  -webkit-appearance: none;
}
</style>