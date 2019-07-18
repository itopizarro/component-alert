<template>
  <div class="placeholder-page">
    <Alert :headline="'Foo'" :content="'<p>Bar <em>baz</em></p>'"></Alert>
    <header>
      <figure class="branding"></figure>
      <nav>
        <p>lorem</p>
        <p>ipsum</p>
        <p>dolor</p>
        <p>sit</p>
      </nav>
    </header>
    <main>
      <figure class="hero"></figure>
      <section>
        <h2>Lorem, ipsum dolor sit amet consectetur adipisicing elit</h2>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus quod dolor doloremque molestiae voluptatibus ex facere accusamus ullam velit quaerat non voluptatem optio autem numquam accusantium laborum inventore, exercitationem neque?</p>
        <div class="grid">
          <div class="card">
            <figure></figure>
            <h3>Lorem ipsum dolor sit amet consectetur.</h3>
          </div>
          <div class="card">
            <figure></figure>
            <h3>Lorem ipsum dolor sit amet consectetur.</h3>
          </div>
          <div class="card">
            <figure></figure>
            <h3>Lorem ipsum dolor sit amet consectetur.</h3>
          </div>
        </div>
      </section>
    </main>
    <footer></footer>
  </div>
</template>

<script>
import Alert from "../components/Alert";
export default {
  name: "PlaceholderPage",
  components: {
    Alert
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.placeholder-page {
  /* border: 2px solid #ccc; */
  margin: 0 auto;
  max-width: 800px;
  text-align: left;
  color: #ccc;
  box-shadow: 0 0 5px 5px #eee;
  /* padding: 20px; */
}

header,
main,
footer {
  margin: 20px;
}

figure {
  /* border: 1px solid red; */
  margin: 0;
  padding: 0;
  background-color: #ddd;
}

.placeholder-page > header {
  display: flex;
  justify-content: space-between;
}

header > nav {
  display: flex;
  justify-content: space-between;
  flex-grow: 1;
  margin-left: 40px;
  text-transform: uppercase;
  align-items: flex-end;
}

nav > p {
  margin: 0;
  font-weight: 700;
}

figure.branding {
  padding-top: 10vw;
  width: 15vw;
}

figure.hero {
  padding-top: 33.3%;
  width: 100%;
}

.grid {
  display: flex;
  margin: 20px 0;
  justify-content: space-between;
}
.grid .card {
  width: calc(33% - 20px);
  margin: 0;
}

.grid .card > figure {
  padding-top: 70%;
}
.grid .card > h3 {
}
</style>
