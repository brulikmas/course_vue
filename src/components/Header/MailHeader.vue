<script setup>
  import css from "./Header.module.css";
  import MailInput from "../Controls/MailInput/MailInput.vue";
  import MailButton from "../Controls/MailButton/MailButton.vue";

</script>

<template>
  <header>
    <ul :class="css.header">
      <li :class="css.header__logo">MasMail</li>
      <li :class="css.header__search">
        <MailInput :styleType="'icon'" placeholder="Поиск сообщений"></MailInput>
      </li>
      <li :class="css.header__help">
        <MailButton :styleType="'icon'">
          <img src="/help.svg" alt="help" height="30" width="30">
        </MailButton>
      </li>
    </ul>
  </header>
</template>

