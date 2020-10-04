<template>
  <div class="layout">
    <div class="columns is-mobile">
      <div
        class="column is-hidden-touch is-2 mb-0 pb-0"
        style="border-right: 1px solid #dbdbdb"
      >
        <div class="sidebar-content-body mx-2 ml-4 mt-4">
          <header style="border-bottom: 1px solid #dbdbdb">
            <div class="level pb-4">
              <div class="level-left">
                <div class="level-item">
                  <div>
                    <h1 class="title is-script has-text-weight-bold">tadka</h1>
                    <p class="mt-2">
                      A list of food experiments <br />
                      tried and teted during <br />
                      the pandemic
                    </p>
                  </div>
                </div>
              </div>
              <div class="level-right">
                <div class="level-item">
                  <p class="is-mono">MENU</p>
                </div>
              </div>
            </div>
          </header>
          <section class="sidebar-content-main mt-4">
            <div>
              <input type="text" class="input" placeholder="Search Dishes" />
            </div>
            <ul class="mt-4 " style=" border-top:1px solid #dbdbdb">
              <li :key="index" v-for="(item, index) in data" style="border-bottom:1px solid #dbdbdb">
                <article class="media py-4" >
                  <div class="media-left">
                    <p class="has-text-weight-bold has-text-grey">
                      {{ index + 1 }}
                    </p>
                  </div>
                  <div class="media-content">
                    <p>{{ item.name }}</p>
                  </div>
                  <div class="media-left">
                    <p class="has-text-weight-bold has-text-grey">
                        ↪</p>
                  </div>
                </article>
              </li>
            </ul>
          </section>
          <footer></footer>
        </div>
      </div>
      <div class="column is-8 is-offset-1">
        <section class="section">
          <div class="container ">
            <slot/>
          </div>
        </section>
      </div>
      <div class="column is-1" style="border-left: 1px solid #dbdbdb">
        <br>
        <ul class="has-text-centered">
          <li class="py-4 is-mono">PRINT</li>
          <li class="py-4 is-mono">SHARE</li>
          <li class="py-4 is-mono">COOK</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import "typeface-corben";
import "typeface-dm-sans";
import "@openfonts/dm-mono_latin";

export default {
  data() {
    return {
      data: [
        {
          name: "Tripe Garlic Infused Paste",
        },
        {
          name: "Cottage Cheese & Cashew Gravy",
        },
      ],
    };
  },
};
</script>
<style>
*,
html {
  font-family: "DM Sans", "Franklin Gothic Medium", "Arial Narrow", Arial,
    sans-serif !important;
    color:black !important;
}

body{
  border-top:10px solid #000;

}

.is-mono {
  font-family: "DM Mono", "Courier New", Courier, monospace !important;
}
.is-script {
  font-family: "Corben", Cambria, Cochin, Georgia, Times, "Times New Roman",
    serif !important;
}
.sidebar-content-body {
  display: flex;
  min-height: 100vh;
  flex-direction: column;
}

/* .box {
  border : 2px solid rgb(245, 245, 245);
} */
.sidebar-content-main {
  flex: 1;
}
</style>
