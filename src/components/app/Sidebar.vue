<template>
  <ul class="sidenav app-sidenav" :class="{ open: modelValue }">
    <router-link 
    v-for="link in links"
    :key="link.url"
    :to="link.url" custom v-slot="{isActive }">
      <li :class="{ active: isActive }">
        <a :href="link.url">
          {{link.title}}
        </a>
      </li>
    </router-link>
  </ul>
</template>

<script>
export default {
  // props: {
  //   modelValue: Boolean
  // },
  props: ['modelValue'],
  data: () => ({
    links: [
      {title: 'Счет', url: '/'},
      {title: 'История', url: '/history'},
      {title: 'Планирование', url: '/planning'},
      {title: 'Новая запись', url: '/record'},
      {title: 'Категории', url: '/categories'}
    ]
  }) 
}
</script>
