<!-- шаблон всего сайта (app) -->
<template>
  <div id="app">
    <!-- вставленный шаблон шапки -->
    <Header />
    <hr>
    <!-- карточки с картинами -->
    <div class="container paintings">
      <h1>Картины эпохи Возрождения</h1>
      <div class="paintings-card">
        <!-- вставленный шаблон карточек с картинами -->
        <CardItem/>
      </div>
    </div>
    <!-- вставленный шаблон подвала -->
    <Footer />
  </div>
</template>

<!-- импортирование всех шаблонов -->
<script>
import CardItem from '@/components/CardItem'
import MenuList from '@/components/MenuList'
import Footer from '@/components/Footer'
import Header from '@/components/Header'

export default {
  name: 'app',
  components: {
    CardItem,
    MenuList,
    Footer,
    Header
  }
}
</script>

<!-- стили шаблона app -->
<style>
/* viewport'ы  */
@media screen and (max-width: 420px) {
  .container {
    margin: 0 1rem;
    padding: 1.75rem 0;
  }

  .mobile img{
    right: 1rem;
  }

  .paintings-card {
    grid-template-columns: repeat(1, 1fr);
  }

}

@media screen and (min-width: 421px) {
  .container {
    margin: 0 3rem;
    padding: 1.75rem 0;
  }

  .mobile img{
    right: 3rem;
  }

  .paintings-card {
    grid-template-columns: repeat(1, 1fr);
  }

}

@media screen and (min-width: 800px) {
  .container {
    margin: 0 6rem;
    padding: 1.75rem 0;
  }

  .mobile img{
    right: 6rem;
  }

  .paintings-card {
    grid-template-columns: repeat(2, 1fr);
  }

}

@media screen and (min-width: 1200px) {
  .container {
    margin: 0 10rem;
    padding: 1.75rem 0;
  }

  .mobile img{
    right: 10rem;
  }

  .paintings-card {
    grid-template-columns: repeat(2, 1fr);
  }

}

@media screen and (min-width: 1440px) {
  .container {
    margin: 0 15rem;
    padding: 1.75rem 0;
  }

  .mobile img{
    right: 15rem;
  }

  .paintings-card {
    grid-template-columns: repeat(2, 1fr);
  }

}

@media screen and (min-width: 1919px) {
  .container {
    margin: 0 22.5rem;
    padding: 1.75rem 0;
  }

  .paintings-card {
    grid-template-columns: repeat(4, 1fr);
  }

}

/* стили для всех элементов сайта */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Merriweather', serif;
}

/* цвет текста в app */
#app{
  color: #343030;
}

/* типография */
h1 {
  font-size: 24px;
  font-weight: 700;
  line-height: 36px;
}

h2 {
  font-size: 18px;
  font-weight: 400;
  line-height: 27px;
}

h3 {
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
}

h4 {
  font-size: 14px;
  font-weight: 700;
  line-height: 21px;
}

h5 {
  font-size: 14px;
  font-weight: 400;
  line-height: 21px;
}

h6 {
  font-size: 14px;
  font-weight: 300;
  line-height: 21px;
}

/* стиль горизонтальной линии */
hr {
  border-top: 1px solid #E1E1E1;
}

/* стиль для кнопок */
button {
  width: 120px;
  height: 50px;
  background-color: #403432;
  border: none;
  color: #F4F6F9;
  cursor: pointer;
  transition: .2s ease-in-out;
  font-family: 'Merriweather', serif;
  font-size: 14px;
}

button:hover {
  background-color: #776763;
}

/* общие стили для шапки и подвала */
header,
footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 14px;
}

header>ul>li,
footer>ul>li {
  cursor: pointer;
}

/* стили для секции с карточками */
.paintings {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  height: 100%;
  justify-content: center;
}

.paintings-card {
  display: grid;
  gap: 2rem;
}
</style>
