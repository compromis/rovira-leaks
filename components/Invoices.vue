<script setup>
import invoices from '../data/invoices.json'
</script>

<template>
  <div class="container">
    <div class="table-wrapper">
      <table class="table">
        <thead>
          <tr>
            <th>Data</th>
            <th>Restaurant</th>
            <th class="text-right">Despesa</th>
            <th class="text-right">👥</th>
            <th width="200">Tipus</th>
            <th>Factura</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="invoice in invoices" :key="invoice.id">
            <td>{{ invoice.date }}</td>
            <td>{{ invoice.restaurant }}</td>
            <td class="text-right">{{ invoice.amount.replaceAll('.', ',') }}</td>
            <td class="text-right">{{ invoice.serves }}</td>
            <td>
              <span v-if="invoice.type.startsWith('Sopar')" class="pill sopar">☾ {{ invoice.type }}</span>
              <span v-else-if="invoice.type === 'Marisqueria'" class="pill marisqueria">🦞 {{ invoice.type }}</span>
            </td>
            <td><a :href="`/invoices/${invoice.file}`" class="pill download">PDF</a></td>
          </tr>
        </tbody>
        <tfoot>
          <tr>
            <th colspan="2">Total</th>
            <th class="text-right">⚠️ <Annotated type="highlight">12.646,98 €</Annotated></th>
            <th colspan="4"></th>
          </tr>
        </tfoot>
      </table>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  margin-top: 5rem;
}

.table-wrapper {
  border: 2px var(--gray-200) solid;
  border-radius: 1rem;
  overflow: clip;
}

.table {
  thead {
    th {
      border-bottom: 2px var(--gray-200) solid;
    }
  }
  tfoot {
    th {
      font-size: 1.25rem;
      border-top: 2px var(--gray-200) solid;
      border-bottom: 0;
    }
  }
}

.text-right {
  text-align: right;
  white-space: nowrap;
}

.pill {
  display: block;
  color: var(--pill-color);
  background: var(--pill-background);
  padding: .15em .3em;
  border-radius: 2rem;
  text-align: center;
  font-weight: 900;
}

.no {
  --pill-color: var(--red);
  --pill-background: #{rgba(#ef404d, .15)};
}

.sopar {
  --pill-color: var(--indigo);
  --pill-background: #{rgba(#6610F7, .15)};
}

.marisqueria {
  --pill-color: var(--blue);
  --pill-background: #{rgba(#55a4db, .15)};
}

.download {
  --pill-color: var(--white);
  --pill-background: var(--gray-600);

  &:hover {
    background: var(--primary);
    color: var(--white);
  }
}

@include media-breakpoint-down(md) {
  .container {
    margin-top: 3rem;
  }

  .table-wrapper {
    overflow: auto;
  }
}
</style>