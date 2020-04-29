<template>
  <q-page padding>
     <q-table
      title="Shopping Lists"
      :data="data"
      :columns="columns"
      row-key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="clothes" :props="props">
            {{ props.row.clothes }}
          </q-td>
          <q-td key="size" :props="props">
            {{ props.row.size }}
          </q-td>
          <q-td key="color" :props="props">
            {{ props.row.color }}
          </q-td>
          <q-td key="price" :props="props">
            {{ props.row.price }}
          </q-td>
          <q-td key="number" :props="props">
            {{ props.row.number }}
          </q-td>
          <q-td key="information" :props="props">
            {{ props.row.information }}
          </q-td>
          <q-td key="payment" :props="props">
            {{ props.row.payment }}
          </q-td>
          <q-td key="actions" :props="props">
            <div class="row">
              <div class="col">
                <q-btn label="Edit" color="green" icon="edit" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Check" color="secondary" icon="check" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Hapus" color="negative" icon="delete" unelevated></q-btn>
              </div>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'clothes',
          required: true,
          label: 'Clothes',
          align: 'left',
          field: 'clothes',
          sortable: true
        },
        { name: 'size', align: 'center', label: 'Size', field: 'size', sortable: true },
        { name: 'color', label: 'Color', align: 'center', field: 'color', sortable: true },
        { name: 'price', label: 'Price', field: 'price', align: 'center', sortable: true },
        { name: 'number', label: 'Number', align: 'center', field: 'number', sortable: true },
        { name: 'information', label: 'Information', align: 'center', field: 'information', sortable: true },
        { name: 'payment', label: 'Payment', align: 'center', field: 'payment', sortable: true },
        { name: 'actions', label: 'Actions', field: 'actions', align: 'center' }
      ],

      data: [
        {
          clothes: 'Sweater rajut',
          size: 'L',
          color: 'Navy',
          price: '299.000',
          number: '1 piece',
          informations: '',
          payment: 'M-banking'
        },
        {
          clothes: 'Jeans',
          size: '30',
          color: 'Army',
          price: '449.000',
          number: '3 pieces',
          informations: 'bubble warps please',
          payment: 'Transfer via Bank BNI'
        }
      ]
    }
  }
}
</script>
