<template>
<div class="container">
    <div class="row">
        <div class="col-md-8 col-md-offset-2">
            <div class="card">
                 <div class="card-header">
                    
                  </div>

                <div class="card-body">
                  <div align="center">
                      <img src="/8796_8955/public/AA_Logo.png" v-bind:style="{  width: '165px', height: '160px' }">
                    <form v-on:submit.prevent="saveForm()" class="form-horizontal" >
                      <div class="form-group">
                        <label for="name" class="col-md-2 control-label" >Nomor Telepon</label>
                        <div class="col-md-4">
                          <input type="text" v-bind:style="{width: '35%' }" class="input is-primary" required="" placeholder="Masukkan Nomor Telepon" v-model="login.no_telp_pegawai"  @input="onlyNumbers" autofocus=""/>
                        <span v-if="errors.no_telp_pegawai" class="help is-danger"> {{ errors.no_telp_pegawai[0]}}</span>
                        </div>
                      </div>
                      <div class="form-group">
                        <label for="name" class="col-md-2 control-label" >Password</label>
                        <div class="col-md-4">
                          <input type="password" v-bind:style="{width: '35%' }" class="input is-primary" required="" placeholder="Masukkan Password" v-model="login.password_pegawai" autofocus=""/>
                        <span v-if="errors.password_pegawai" class="help is-danger"> {{ errors.password_pegawai[0]}}</span>
                        </div>
                      </div>
                     
                      <br>
                      <div class="form-group">
                        <div class="col-md-4 col-md-offset-2">
                          <button class="button is-info" type="submit">Login</button>
                        </div>
                      </div>
                      <br>
                    </form>
                  </div>
                </div>
            </div>
        </div>
    </div>
    <footer class="footer">
        <div class="content has-text-centered">
          <p>
            <strong>SIBA ©2019</strong> 
          </p>
        </div>
    </footer>
</div>

</template>


<script>
  export default {
    data: function() {
      return {
        login: {
            no_telp_pegawai: '',
            password_pegawai: '',
        },
        errors: [],
        message: ''
      }
    },
    mounted()  {
     var app = this;
    },
    methods: {
      alert(pesan){
        this.$swal({
          title: "Berhasil Login",
          text: pesan,
          icon: "success"
        });
      },
      saveForm(){
        axios.post('/8796_8955/public/api/pegawai/loginweb',{
             no_telp_pegawai:this.login.no_telp_pegawai,
             password_pegawai:this.login.password_pegawai
        })
        .then((resp) => {
        //if(resp.response.status == 200)
          this.alert('Selamat');
          this.$router.push('/');
        })
        .catch((resp) =>{
          if(resp.response.status == 404) alert('Gagal Login');
          this.errors = resp.response.data.errors;
          console.log(resp);
        });
      },
       onlyNumbers: function() {
       this.login.no_telp_pegawai = this.login.no_telp_pegawai.replace(/[^0-9]/g,'');
      }
    }
  }

</script>