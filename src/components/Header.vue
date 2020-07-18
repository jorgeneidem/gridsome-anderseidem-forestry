<template>
  <header
    class="header"
    :class="{
      sticky: $route.path === '/' || $route.path.includes('/projects/'),
    }"
  >
    <div class="container">
      <div class="left">
        <g-link :to="{ name: 'home' }" class="home-link">
          <span class="logotype"
            ><h1><strong>Anders Eidem</strong> Fotograf</h1></span
          >
        </g-link>
      </div>
      <nav class="nav right">
        <g-link class="nav__link" to="/journal">Blogg</g-link>
        <g-link class="nav__link" to="/contact">Kontakt</g-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      logo: require("../../static/logo.svg"),
      settings: require("../../data/theme.json"),
    };
  },
};
</script>

<style scoped>
.header {
  position: relative;
  height: 4rem;
  z-index: 10;
}
.header.sticky {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  backdrop-filter: invert(1%) blur(10px);
  background-color: rgba(255, 255, 255, 0.25);
}
.header > .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100%;
}
.home-link {
  text-decoration: none;
}
.logo {
  height: 1.5rem;
}
.logotype h1 {
  font-size: 0.9rem;
  font-weight: normal;
}
.site-name {
  font-size: 0.9rem;
  font-weight: 700;
  letter-spacing: 0.05em;
  text-decoration: none;
  text-transform: uppercase;
}
.nav > * {
  font-size: 0.9rem;
  font-weight: 600;
  text-decoration: none;
  margin-top: 4px;
  margin-right: 0.8rem;
  padding-bottom: 4px;
  border-bottom: 1px solid;
  border-color: transparent;
  transition: border 0.15s;
}
.nav > *:last-of-type {
  margin: 0;
}
.nav > *:hover {
  border-color: inherit;
}
.nav > .active {
  border-color: inherit;
}
</style>
