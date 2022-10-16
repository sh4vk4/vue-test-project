<!-- шаблон списка ссылок -->
<template>
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
</template>

<style>
/* viewport'ы */
@media screen and (min-width: 1200px) {
  ul {
    grid-template-columns: repeat(5, 95px);
    gap: 2.5rem;
  }
}

@media screen and (min-width: 1440px) {
  ul {
    grid-template-columns: repeat(5, 1fr);
    gap: 2.5rem;
  }
}

@media screen and (max-width: 1200px) {
  
}

@media screen and (max-width: 1549px) {
  header ul {
    display: none;
  }
  ul {
    grid-template-columns: repeat(2, 1fr);
    row-gap: 1rem;
    column-gap: 2.5rem;
  }

}

/* стиль для списка ссылок */
ul {
  list-style: none;
  display: grid;
}

/* стиль для элемента списка ссылок */
li {
  cursor: pointer;
}
</style>