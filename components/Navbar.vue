<template>
  <nav class="nav">
    <span
      class="nav-toggle"
      @click="toggleActive"
    >
      <i class="fas" :class="{'fa-bars': !isActive, 'fa-times': isActive }" />
    </span>
    <a class="nav-logo" href="#home">
      George's
    </a>
    <ul class="nav-main" :class="{'is-active': isActive }">
      <li class="nav-link">
        <a href="#home">
          Home
        </a>
      </li>
      <li class="nav-link">
        <a href="#menu">
          Menu
        </a>
      </li>
      <li class="nav-link">
        <a href="#hours_location">
          Hours & Locations
        </a>
      </li>
      <li class="nav-link">
        <a href="#about">
          About
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data: function() {
    return {
      isActive: false
    }
  },
  methods: {
    toggleActive() {
      this.isActive = !this.isActive
    }
  }
}
</script>

<style lang="scss" scoped>
.nav {
  background: #fff;
  box-shadow: 0px -1px 2px 0px rgba(0, 0, 0, 0.25);
  font-size: 1rem;
  font-weight: 700;
  padding-bottom: 0.5rem;

  .nav-toggle {
    color: #111;
    cursor: pointer;
    font-size: 2rem;
    position: absolute;
    right: 1rem;
    top: 0.5rem;
    transition: color 0.3s ease-in-out;

    &:hover,
    &:active {
      color: rgb(207, 25, 25);
    }
  }

  .nav-logo {
    color: #111;
    display: inline-block;
    font-size: 2rem;
    margin-left: 1rem;
    margin-top: 0.5rem;
    text-decoration: none;
  }

  .nav-main {
    list-style-type: none;
    display: none;

    .nav-link {
      transition: transform 0.3s ease-in-out;
      text-align: center;
      margin: 1rem auto;

      &:hover {
        transform: scale(1.05);
      }

      a {
        color: #111;
        text-decoration: none;
        padding: 1rem auto;
        transition: color 0.3s ease-in-out;

        &:hover,
        &:active {
          color: rgb(207, 25, 25);
        }
      }
    }
  }

  .is-active {
    display: block;
  }
}

@media screen and (min-width: 768px) {
  .nav {
    display: flex;
    justify-content: space-between;
    padding-bottom: 0;
    height: 70px;
    align-items: center;

    .nav-toggle {
      display: none;
    }

    .nav-logo {
      margin-top: 0;
    }

    .nav-main {
      display: flex;
      margin-right: 30px;
      flex-direction: row;
      justify-content: flex-end;

      li {
        margin: 0;
      }

      .nav-link {
        margin-left: 40px;
      }
    }
  }
}
</style>
