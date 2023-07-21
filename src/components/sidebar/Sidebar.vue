<template>
  <div class="sidebar">
    <ul class="sidebar__menu">
      <li class="sidebar__menu-item">
        <router-link class="sidebar__menu-link sidebar__menu-link--album"
                     :to="{ name: 'Vacation' }">
          <i class="icon"></i>
        </router-link>
      </li>
      <li class="sidebar__menu-item">
        <router-link class="sidebar__menu-link sidebar__menu-link--mail"
                     :to="{ name: 'Vacation' }">
          <i class="icon"></i>
        </router-link>
      </li>
      <li class="sidebar__menu-item">
        <router-link class="sidebar__menu-link sidebar__menu-link--messages-square"
                     :to="{ name: 'Vacation' }">
          <i class="icon"></i>
        </router-link>
      </li>
      <li class="sidebar__menu-item">
        <router-link class="sidebar__menu-link sidebar__menu-link--folder-clock"
                     :to="{ name: 'Vacation' }">
          <i class="icon"></i>
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
}
</script>

<style lang="scss">
@import './Sidebar.scss';
</style>
