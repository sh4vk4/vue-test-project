<!-- шаблон подвала -->
<template>
  <footer id="footer">
    <!-- вставленный шаблон ссылок -->
    <MenuList />
    <!-- контакты и адрес -->
    <div class="contact">
      <p><img src="../assets/phone.svg" alt=""> +7 (812) 555-55-55</p>
      <p><img src="../assets/address.svg" alt=""> г. Санкт-Петербург, ул. Ефимова, 3</p>
    </div>
  </footer>
</template>

<!-- импортирование шаблона ссылок -->
<script>
import MenuList from '@/components/MenuList'
export default {
  name: 'footer',
  components: {
    MenuList
  }
}
</script>

<style>
/* viewport'ы */
@media screen and (max-width: 425px) {
  footer {
    padding: 1.75rem 1rem;
    flex-direction: column;
    gap: 2.5rem;
  }

  .contact {
    gap: 2rem;
    flex-direction: column;
  }
}

@media screen and (min-width: 426px) {
  footer {
    padding: 1.75rem 3rem;
    gap: 2.5rem;
  }

  .contact {
    gap: 2rem;
    flex-direction: column;
  }
}

@media screen and (min-width: 800px) {
  footer {
    padding: 1.75rem 6rem;
    gap: 2.5rem;
  }
}

@media screen and (min-width: 1200px) {
  footer {
    padding: 1.75rem 10rem;
    gap: 2.5rem;
  }
}

@media screen and (min-width: 1440px) {
  footer {
    padding: 1.75rem 15rem;
    gap: 2.5rem;
  }
}

@media screen and (min-width: 1919px) {
  footer {
    padding: 1.75rem 22.5rem;
    gap: 2.5rem;
  }

  .contact {
    flex-direction: row;
  }
}

/* стиль для подвала */
footer {
  background-color: #ECEAEA;
  width: 100%;
}

/* стиль для контакта и адреса */
.contact {
  display: flex;
}

.contact p {
  display: flex;
  align-items: center;
  gap: .5rem
}
</style>