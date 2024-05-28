<template>
  <div class="q-pa-md">
    <q-carousel
      swipeable
      animated
      v-model="slide"
      thumbnails
      infinite
    >
      <q-carousel-slide :name="1" img-src="/images/gambar 1.jpg" />
      <q-carousel-slide :name="2" img-src="/images/gambar 3.jpg" />
      <q-carousel-slide :name="3" img-src="/images/gambar 2.jpg" />
      <q-carousel-slide :name="4" img-src="/images/gambar 4.jpg" />
    </q-carousel>
  </div>
  
  <div class="landing-page">
    <!-- Header -->
    <header class="header">
      <nav class="nav">
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Games</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">Game Store Sadam</h1>
        <p class="hero-subtitle">Belanja game online sekarang!</p>
        <button class="hero-button">Belanja Sekarang!</button>
      </div>
    </section>

    <!-- Featured Games Section -->
    <section class="featured-games">
      <h2 class="featured-games-title">Game Terbaru</h2>
      <div class="featured-games-grid">
        <div class="featured-game" v-for="game in featuredGames" :key="game.id">
          <img :src="game.image" alt="Game Image">
          <h3>{{ game.title }}</h3>
          <p>{{ game.description }}</p>
          <button class="featured-game-button">Beli Sekarang!</button>
        </div>
      </div>
    </section>

    <!-- Additional Card -->
    <div class="q-pa-md row items-start q-gutter-md">
      <q-card class="my-card" flat bordered>
        <q-img
          src="/images/gambar 8.jpg"
        />

        <q-card-section>
          <div class="text-overline text-orange-9">Game Store Sadam</div>
          <div class="text-h5 q-mt-sm q-mb-xs">by : Sadam</div>
          <div class="text-caption text-grey">
            Game Store Sadam Adalah Toko Online Game Termurah Sedunia.
          </div>
        </q-card-section>

        <q-card-actions>
          <q-btn flat color="primary" label="Share" />
          <q-btn flat color="secondary" label="Book" />

          <q-space />

          <q-btn
            color="grey"
            round
            flat
            dense
            :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
            @click="expanded = !expanded"
          />
        </q-card-actions>

        <q-slide-transition>
          <div v-show="expanded">
            <q-separator />
            <q-card-section class="text-subtitle2">
              {{ lorem }}
            </q-card-section>
          </div>
        </q-slide-transition>
      </q-card>
    </div>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 Game Store Sadam</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0, // Ini untuk mengatur slide default pada carousel
      featuredGames: [
        {
          id: 1,
          title: "Free Fire",
          image: "/images/gambar 5.jpg",
          description: "Free Fire adalah game terbaru yang sangat menarik!"
        },
        {
          id: 2,
          title: "The Sims 2",
          image: "/images/gambar 6.jpg",
          description: "The Sims 2 adalah game yang sangat populer!"
        },
        {
          id: 3,
          title: "GTA 5",
          image: "/images/gambar 7.jpg",
          description: "GTA 5 adalah game yang sangat menarik!"
        }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 350px
</style>

<style scoped>
.landing-page {
  font-family: Arial, sans-serif;
  text-align: center;
}

.header {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  text-align: center;
}

/* CSS untuk navigasi yang berada di tengah dan sejajar */
.nav {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  margin: 0 20px;
}

.nav a {
  color: #fff;
  text-decoration: none;
  padding: 10px;
  font-size: 1.2rem;
}

.nav a:hover {
  background-color: #555;
  border-radius: 5px;
}

/* CSS untuk hero section */
.hero {
  background-image: url("/images/gambar 9.jpg");
  background-size: cover;
  background-position: center;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}

.hero-content {
  text-align: center;
}

.hero-title {
  font-size: 3rem;
  font-weight: bold;
  color: black; /* Mengubah warna teks menjadi hitam */
}

.hero-subtitle {
  font-size: 1.5rem;
}

.hero-button {
  background-color: #333;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  font-size: 1.5rem;
  cursor: pointer;
}

/* CSS untuk featured games section */
.featured-games {
  background-color: #f7f7f7;
  padding: 2rem;
}

.featured-games-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.featured-game {
  background-color: #fff;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 0.5rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.featured-game img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 0.5rem 0.5rem 0 0;
}

.featured-game h3 {
  font-size: 1.5rem;
  font-weight: bold;
  margin-top: 0.5rem;
}

.featured-game p {
  font-size: 1rem;
  color: #666;
}

.featured-game-button {
  background-color: #333;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  font-size: 1.5rem;
  cursor: pointer;
}

/* CSS untuk footer */
.footer {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  text-align: center;
}
</style>
