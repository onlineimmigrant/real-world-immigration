<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="layout">
    <header>
      <div class="wrapper">
        <nav>
          <RouterLink :to="{ name: 'event-list' }">Events</RouterLink> |
          <RouterLink :to="{ name: 'about' }">About</RouterLink>
        </nav>
      </div>
    </header>
    <RouterView />
  </div>
</template>

<style>
#layout {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  font-weight: 300;
  color: #2c3e50;
}

.col {
  flex: 1;
  padding: 10px;
}


.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

}

.card {
  width: 90%;
  min-width: 360px;
  max-width: 400px;
  height: auto;
  box-shadow: 0px 0px 5px gray;
  border-radius: 5px;
  overflow: hidden;
  margin: 20px auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #2c3e50;
  color: white;
}

.card-image {
  width: 100%;
  height: auto;
  background-size: cover;
  background-position: center;
}

.card-header {
  padding: 1rem;
  background: linear-gradient(to right, #2c3e50, #47637e);
  width: 100%;
  font-weight: bolder;
  font-size: 12px;
  margin-left: 30px;
  text-align: left;

}

.card-title {
  width: 90%;
  font-size: 24px;
  font-weight: bold;
  margin-top: 20px;
  text-align: left;
}

.card-text {
  width: 90%;
  font-size: 16px;
  margin: 5px;
  text-align: right;
  font-weight: 100;
}

.card-footer {
  width: 90%;
  font-size: 12px;
  margin: 5px;
  text-align: right;
  font-weight: 100;
}

.container {
  display: flex;
  flex-wrap: wrap;
}


.card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
  color: #2c3e50;
  text-decoration: none;
}



@media (max-width: 767px) {
  .col {
    flex-basis: 100%;
  }

  .card {
    width: 100%;
    margin-right: 0;
    margin-bottom: 20px;
  }

  .card-title {
    font-size: 20px;
  }

  .card-text {
    font-size: 16px;
  }

  .card-footer {
    width: 90%;
    font-size: 12px;
    margin: 5px;
    text-align: right;
    font-weight: 100;
  }

  .card-image {
    min-height: 80%;
    height: auto;
  }

}


.container {
  display: flex;
  flex-wrap: wrap;
}

h2 {
  font-size: 24px;
}

.row {
  display: flex;
  flex-wrap: wrap;
  margin: -10px;
}

.col {
  flex: 1;
  padding: 10px;
}

@media (max-width: 767px) {
  .col {
    flex-basis: 100%;
  }

  .card {
    width: 100%;
    margin-right: 0;
    margin-bottom: 20px;
  }

  .card-title {
    font-size: 20px;
  }

  .card-text {
    font-size: 16px;
  }

  .card-footer {
    width: 90%;
    font-size: 12px;
    margin: 5px;
    text-align: right;
    font-weight: 100;
  }

  .card-image {
    min-height: 80%;
    height: auto;
  }
}

.card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}


.row {
  display: flex;
  flex-wrap: wrap;
  margin: -10px;

}

.gradient-primary {
  color: linear-gradient(195deg, #ec407a 0%, #d81b60 100%);
}

.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.mobile-nav {
  display: none;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(255, 255, 255, 1);
  opacity: 0.8;
  color: #fff;
  padding: 20px 0;
  display: flex;
  justify-content: space-between;
  width: 100%;
}

@media only screen and (max-width: 767px) {
  .mobile-nav {
    display: flex;
  }
}

.mobile-nav a {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 25%;
}

.mobile-nav-size {
  width: 30px;
  height: 30px;
}
</style>