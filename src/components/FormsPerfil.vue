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
    <label for="nomeField">Nome:</label>
    <input type="text"  id="nomeField" v-model="user.nome" required>
    <br>
    <label for="sobrenomeField">Sobrenome:</label>
    <input type="text"  id="sobrenomeField" v-model="user.sobrenome" required>
    <br>
    <label for="dataField">Data:</label>
    <input type="date"  id="dataField" v-model="user.data" required>
    <br>
    <label for="emailField">Email:</label>
    <span class="input-group-text" id="emailFieldPrepend"></span>
    <input type="email" class="form-control" id="emailField" aria-describedby="emailFieldPrepend" v-model="user.email" required>
    <br>
    <label for="senhaField">Senha</label>
    <input type="text" class="form-control" id="senhaField" v-model="user.senha" />
    <br>
    <label for="senhaconfirmField">Confirmar senha</label>
    <input type="text" class="form-control" id="senhaconfirmField" v-model="user.senhaconfirm" />
    <br>
    <label for="cidadeField" >Cidade</label>
    <input type="text" class="form-control" id="cidadeField" v-model="user.cidade" />
    <br>
    <label for="estadoField">Estado</label>
      <select class="form-select" id="estadoField" v-model="user.estado">
        <option selected disabled value="">Selecionar...</option>
        <option v-for="estado of estados" :key="estado.uf" :value="estado.uf">
                {{ estado.name }}
        </option>
      </select>
    <br> 
    <label for="ruaField">Rua:</label>
    <input type="text" class="form-control" id="ruaField" v-model="user.rua" />
    <br>
    <label for="bairroField">Bairro</label>
    <input type="text" class="form-control" id="bairroField" v-model="user.bairro" />
    <br>
    <label for="biografiaField">Biografia</label>
    <input type="text" class="form-control" id="biografiaField" v-model="user.biografia" />
    <br>
    <div >
      <p>Hobbies</p>
      <div class="row-selection"><label for="hobbiesField">Esportes</label><input
              type="checkbox"
              id="hobbiesField"
              value="esportes"
              v-model="user.hobbies"
            /></div>
      <div class="row-selection"><label for="hobbiesField">Música</label><input
              type="checkbox"
              id="hobbiesField"
              value="música"
              v-model="user.hobbies"
            /></div>
      <div class="row-selection"><label for="hobbiesField">Viagens</label><input
              type="checkbox"
              id="hobbiesField"
              value="viagens"
              v-model="user.hobbies"
            />
            </div>
            <div class="row-selection"><label for="hobbiesField">Leitura</label><input
              type="checkbox"
              id="hobbiesField"
              value="leitura"
              v-model="user.hobbies"
            /></div>
          </div>
  </form>
</template>



<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap");

</style>