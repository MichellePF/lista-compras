<template>
  <q-page class="bg-grey-3 column">
    <!-- Lista de Items -->
    <q-list class="bg-white q-pa-md" separator bordered>
      <q-item v-for="(item, i) in items" :key="i" tag="label" v-ripple>
        <q-item-section avatar>
          <q-checkbox v-model="item.listo" color="teal" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{item.texto}}</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'Index',
  data () {
    return {
      items: [
        {
          texto: 'Cloro',
          listo: false
        },
        {
          texto: 'Pan batido',
          listo: false
        },
        {
          texto: 'Chocolate',
          listo: false
        }
      ]
    }
  }
}
</script>
