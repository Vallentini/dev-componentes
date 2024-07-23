<script setup>
import InfoForm from '@/components/InfoForm.vue'
import { ref } from 'vue'

const title = ref("Seu perfil");
const user = ref({
  nome: '',
  sobrenome: '',
  data: '',
  email: '',
  senha: '',
  senhaconfirm: '',
  cidade: '',
  estado: '',
  rua: '',
  bairro:'',
  hobbies: [],
  linguagempref: ''
})

const estados = [
  { uf: 'AC', name: 'Acre' },
  { uf: 'AL', name: 'Alagoas' },
  { uf: 'AP', name: 'Amapá' },
  { uf: 'AM', name: 'Amazonas' },
  { uf: 'BA', name: 'Bahia' },
  { uf: 'CE', name: 'Ceará' },
  { uf: 'DF', name: 'Distrito Federal' },
  { uf: 'ES', name: 'Espírito Santo' },
  { uf: 'GO', name: 'Goiás' },
  { uf: 'MA', name: 'Maranhão' },
  { uf: 'MT', name: 'Mato Grosso' },
  { uf: 'MS', name: 'Mato Grosso do Sul' },
  { uf: 'MG', name: 'Minas Gerais' },
  { uf: 'PA', name: 'Pará' },
  { uf: 'PB', name: 'Paraíba' },
  { uf: 'PR', name: 'Paraná' },
  { uf: 'PE', name: 'Pernambuco' },
  { uf: 'PI', name: 'Piauí' },
  { uf: 'RJ', name: 'Rio de Janeiro' },
  { uf: 'RN', name: 'Rio Grande do Norte' },
  { uf: 'RS', name: 'Rio Grande do Sul' },
  { uf: 'RO', name: 'Rondônia' },
  { uf: 'RR', name: 'Roraima' },
  { uf: 'SC', name: 'Santa Catarina' },
  { uf: 'SP', name: 'São Paulo' },
  { uf: 'SE', name: 'Sergipe' },
  { uf: 'TO', name: 'Tocantins' }
]


const mostrarPerfil = ref(false)

function salvarPerfil() {
  mostrarPerfil.value = true
}
</script>

<template>
  <form action="">
    <h1>Perfil</h1>
    <label class="label-form" for="nomeField">Nome:</label>
    <input class="ipunt-form" type="text"  id="nomeField" v-model="user.nome" required>
    <label class="label-form" for="sobrenomeField">Sobrenome:</label>
    <input class="ipunt-form" type="text"  id="sobrenomeField" v-model="user.sobrenome" required>
    <label class="label-form" for="dataField">Data:</label>
    <input class="ipunt-form" type="date"  id="dataField" v-model="user.data" required>
    <label class="label-form" for="emailField">Email:</label>
    <span class="input-group-text" id="emailFieldPrepend"></span>
    <input class="ipunt-form" type="email" id="emailField" aria-describedby="emailFieldPrepend" v-model="user.email" required>
    <label class="label-form" for="senhaField">Senha</label>
    <input class="ipunt-form" type="text" id="senhaField" v-model="user.senha" />
    <label class="label-form" for="senhaconfirmField">Confirmar senha</label>
    <input class="ipunt-form" type="text" id="senhaconfirmField" v-model="user.senhaconfirm" />
    <label class="label-form" for="cidadeField" >Cidade</label>
    <input class="ipunt-form" type="text" id="cidadeField" v-model="user.cidade" />
    <label class="label-form" for="estadoField">Estado</label>
      <select class="form-select" id="estadoField" v-model="user.estado">
        <option selected disabled value="">Selecionar...</option>
        <option v-for="estado of estados" :key="estado.uf" :value="estado.uf">
                {{ estado.name }}
        </option>
      </select>
    <br> 
    <label class="label-form"  for="ruaField">Rua:</label>
    <input class="ipunt-form" type="text" id="ruaField" v-model="user.rua" />
    <label class="label-form" for="bairroField">Bairro</label>
    <input class="ipunt-form" type="text" id="bairroField" v-model="user.bairro" />
    <label class="label-form" for="biografiaField">Biografia</label>
    <input class="ipunt-form" type="text" id="biografiaField" v-model="user.biografia" />
    <div >
      <p>Hobbies</p>
      <div class="row-selection">
        <label class="label-form" for="hobbiesField">Esportes</label>
        <input class="ipunt-form" type="checkbox" id="hobbiesField" value="esportes" v-model="user.hobbies"></div>
      <div class="row-selection">
        <label class="label-form" for="hobbiesField">Música</label>
        <input class="ipunt-form" type="checkbox" id="hobbiesField" value="música" v-model="user.hobbies"/></div>
      <div class="row-selection">
        <label class="label-form" for="hobbiesField">Viagens</label>
      <input class="ipunt-form" type="checkbox" id="hobbiesField" value="viagens" v-model="user.hobbies"/></div>
      <div class="row-selection">
        <label class="label-form" for="hobbiesField">Leitura</label>
        <input class="ipunt-form" type="checkbox" id="hobbiesField" value="leitura" v-model="user.hobbies"/></div>
      </div>
      <div >
        <p>Linguagem preferida</p>
        <div>
          <label class="label-form" for="langC">C</label>
          <input class="ipunt-form" type="radio" v-model="user.linguagempref" value="C" id="langC"/></div>
        <div>
          <label class="label-form" for="langJava">Java</label> 
          <input class="ipunt-form" type="radio" v-model="user.linguagempref" value="Java" id="langJava"/>
        </div>
        <div>
          <label class="label-form" for="langPython">Python</label>
          <input class="ipunt-form" type="radio" v-model="user.linguagempref" value="Python" id="langPython"/></div>
        <div>
          <label class="label-form" for="langJs">JavaScript</label>
          <input class="ipunt-form" type="radio" v-model="user.linguagempref" value="Javascript" id="langJs"/>
        </div>
      </div>
      <div>
        <button class="botao"  type="submit">Enviar</button>
      </div>
  </form>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');

form {
  width: 40%;
  margin: auto;
  margin-top: 20px;
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  border-radius: 20px;
  font-family: "Lobster", sans-serif;
  font-weight: 400;
  font-style: normal;
  background-color:rgb(195, 214, 248);;                    
}
.label-form {
font-size: 20px;
margin-top: 15px;
margin-right: 2px;
}

.input-form {
  margin-bottom: 15px;

}

.botao{
  background-color: rgb(228, 255, 246);
  margin-top: 5px;
  width: 100px;
  height: 40px;
  font-family: "Lobster", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 20px;
  margin-bottom: 10px;
}

p{
  font-size: 20px;
  margin: auto;
  padding-bottom: 10px;
  margin-top: 10px;
}

</style>