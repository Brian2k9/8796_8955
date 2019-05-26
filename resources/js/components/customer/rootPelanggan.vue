<template>
<div class="content" id="homePelanggan">  
<nav class="navbar is-dark" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a>
      <img src="/8796_8955/public/AA_Logo.png" v-bind:style="{ marginLeft: '60px', width: '65px', height: '60px' }">
   </a>
    <a class="navbar-item">
        
        <p> SIBA </p>
    </a>

    <a role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      
    </a>
  </div>

  <div id="navbarBasicExample" class="navbar-menu">
   <div class="navbar-start">
    
      <a class="navbar-item">
        <router-link to= "/customer_page" class="button is-dark"><i class="fas fa-home"></i> &nbsp; Home</router-link>
      </a>

      <a class="navbar-item">
        <router-link to= "/customer_page/daftar_sparepart" class="button is-dark"><i class="fas fa-cogs"></i> &nbsp; Daftar Sparepart</router-link>
      </a>

       <a class="navbar-item">
        <router-link to= "/customer_page/riwayat_pelanggan" class="button is-dark"><i class="fas fa-clipboard-list"></i> &nbsp; Riwayat Pelanggan</router-link>
      </a>

      <a class="navbar-item">
        <router-link to= "/customer_page/about" class="button is-dark"><i class="fas fa-info-circle"></i> &nbsp; About Us</router-link>
      </a>
       
     </div>
    
    
    <div class="navbar-end">
      
    </div>
  </div>
</nav>

        <div id="appPage">
            <main class="pageContent">
            <transition name="fade">
            <router-view></router-view>
            </transition>
            </main>
        </div>
        <br>
        
        <footer class="footer">
        <div class="content has-text-centered">
          <p>
            <strong>Halaman Pelanggan SIBA ©2019</strong> 
          </p>
        </div>
        </footer>
        
</div>

 
</template>

<script>

    export default{
    }
</script>

<style>
  
</style>