<template>
  <div>
    <q-form ref="formRede" @submit="cadastrar" class="bg">
      <!-- div class="bg"></div> -->
      <div class="main-container">
        <div class="q-mb-md">
          <h4 class="title">Cadastrar Rede</h4>
          <div class="divisor-inline"></div>
        </div>
        <div class="q-pa-md">
          <div class="row q-col-guter-lg q-mb-sm">
            <div class="col-2">
              <q-input
                :rules="[(val) => !(val == null || val == '') || 'Campo Obrigatorio']"
                v-model="rede.codigo"
                label="Codigo"
                dense
              />
            </div>
            <div class="col-6">
              <q-input
                :rules="[(val) => !(val == null || val == '') || 'Campo Obrigatorio']"
                v-model="rede.nome"
                label="Nome"
                dense
              />
            </div>
            <div class="col-2">
              <q-input
                :rules="[(val) => !(val == null || val == '') || 'Campo Obrigatorio']"
                v-model="rede.tensao_normal"
                label="Tensao Normal"
                dense
              />
            </div>
          </div>
        </div>
        <div>
          <div class="row">
            <div class="col-12">
              <div style="float: right">
                <q-btn style="margin-right: 10px" label="Voltar" no-caps class="btn-voltar" />
                <q-btn type="submit" label="Cadastrar" no-caps class="btn-cadastrar" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </q-form>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'CreateEditRedes',
  setup() {
    const rede = ref({
      codigo: null,
      nome: null,
      tensao_normal: null,
    })

    return {
      rede,
    }
  },
  methods: {
    cadastrar() {
      console.log(this.rede)
      console.log('invocou o metodo cadastrar. ')
    },
  },
}
</script>
