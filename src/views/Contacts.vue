<template>
<div class="main">
  <div class="page-wrapper">
    <h1 class="heading">Контакты</h1>
    <div class="contacts__wrapper">
      <div style="position:relative;overflow:hidden;"><a href="https://yandex.ru/maps/org/baza_otdykha_kaspiyskiy_lotos/132383601062/?utm_medium=mapframe&utm_source=maps" style="color:#eee;font-size:12px;position:absolute;top:0px;">База отдыха Каспийский лотос</a><a href="https://yandex.ru/maps/10946/astrakhan-oblast/category/resort/184106400/?utm_medium=mapframe&utm_source=maps" style="color:#eee;font-size:12px;position:absolute;top:14px;">Дом отдыха в Астраханской области</a><iframe src="https://yandex.ru/map-widget/v1/-/CCU5YNgGhA" width="600" height="360" frameborder="0" allowfullscreen="true" style="position:relative;"></iframe></div>
      <div>
        <p class="contacts__text">
          Расстояние до ближайшего аэропорта 80 км, а до железнодорожного вокзала около 89 км езды. Гостям базы отдыха доступна бесплатная парковка.
        </p>
        <p class="contacts__text">
          По запросу предоставляется трансфер.
        </p>
        <p class="contacts__text">
          Еmail: <a href="#">caspianlotus@gmail.com</a>
        </p>
        <p class="contacts__text">
          Телефон: <a href="#">+7 (700) 001-18-88</a>
        </p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "Contacts"
}
</script>

<style lang="scss">
.contacts {
  &__wrapper {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  &__text {
    max-width: 400px;
  }
}
</style>