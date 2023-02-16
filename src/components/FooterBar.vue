<template>
  <body>
    <div id="app">
      <header>
        <!-- Your website header content goes here -->
      </header>

      <main>
        <!-- Your website main content goes here -->
        <div class="container">
          <!-- Your cards with items go here -->
        </div>
      </main>

      <footer class="footbar">
        <div class="container">
          <div class="row">
            <div class="col-md-6">
              <p>&copy; Copyright.</p>
            </div>
            <div class="col-md-6">
              <ul class="list-inline text-md-right">
                <li class="list-inline-item">
                  <a href="/" style="color: orangered; text-decoration: none"
                    >Home</a
                  >
                </li>
                <li class="list-inline-item">
                  <a
                    href="/team"
                    style="color: orangered; text-decoration: none"
                    >Team</a
                  >
                </li>
              </ul>
            </div>
          </div>
        </div>
      </footer>
    </div>
  </body>
</template>

<style scoped>
.footbar ul li a {
  color: orangered;
}
.footbar {
  background: rgb(43, 43, 43);
  justify-content: space-between;
  font-size: 18px;
  padding: 30px;
  text-align: center;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
}
body {
  display: flex;
  flex-direction: column;
  min-height: 10vh;
}
.col-md-6 {
  color: red;
}
</style>
