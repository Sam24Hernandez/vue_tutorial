<template>
    <header id="header">
      <div class="center">
        <!-- LOGO -->
        <div id="logo">
          <img
            src="../assets/logo.png"
            alt="Logotipo"
            class="app-logo"
          />
          <span id="brand"> <strong>Vue</strong>Web</span>
        </div>
        <!-- MENU -->
        <nav id="menu">
          <ul>
            <li>
              <a href="index.html">Inicio</a>
            </li>
            <li>
              <a href="form.html">Acerca</a>
            </li>
            <li>
              <a href="blog.html">Blog</a>
            </li>
            <li>
              <a href="#">Contacto</a>
            </li>
          </ul>
        </nav>
        <!--.clearfix-->
        <div class="clearfix"></div>
      </div>
    </header>
</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>