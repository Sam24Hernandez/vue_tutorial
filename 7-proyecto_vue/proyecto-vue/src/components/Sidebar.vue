<template>
  <div class="center">
      <section id="content">
        <h2 class="subheader">Últimos artículos</h2>
        <!-- listado de articulos -->
        <div id="articles">
          <article class="article-item" id="article-template">
            <div class="image-wrap">
              <img
                src="https://unhabitatmejor.leroymerlin.es/sites/default/files/styles/header_category/public/2018-10/4%20paisaje%20macedonia.jpg?itok=AELknmF8"
                alt="Paisaje"
              />
            </div>
            <h2>Titulo del Artículo</h2>
            <span class="date-article"> Hace 5 minutos </span>
            <a href="article.html">
              Leer más
              <svg
                height="12"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 4.53657 8.69699"
                class="css-b7q1rs"
              >
                <path
                  d="
                  M.18254,8.697a.18149.18149,0,0,1-.12886-.31034L4.09723,4.34126.05369.29954a.18149.18149,
                  0,0,1,.2559-.2559L4.4838,4.21785a.18149.18149,0,0,1,0,.2559L.30958,8.648A.18149.18149,
                  0,0,1,.18254,8.697Z
                "
                  fill="currentColor"
                ></path>
              </svg>
            </a>
            <div class="clearfix"></div>
          </article>
        </div>
      </section>

      <aside id="sidebar">
        <div id="nav-blog" class="sidebar-item">
          <h3>Puedes hacer esto:</h3>
          <a href="form.html">Crear artículo</a>
        </div>

        <div id="search" class="sidebar-item">
          <h3>Buscador:</h3>
          <p>Encuentra el artículo que buscas</p>
          <form>
            <input
              type="search"
              placeholder="Buscar..."
              class="search-section"
              name="search"
            />
            <input
              type="submit"
              class="search-button"
              value="Buscar"
              name="submit"
            />
          </form>
        </div>
      </aside>
      <div class="clearfix"></div>
    </div>
</template>

<script>
export default {
    name: "Sidebar",
}
</script>