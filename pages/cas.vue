<script setup lang="ts">
useHead({
  htmlAttrs: {
    lang: 'es',
  },
})

useSeoMeta({
  title: 'RoviraLeaks - Compromís',
  ogTitle: 'RoviraLeaks - Compromís',
  description: 'Destapem que el pitjor Conseller d’Educació de la història, José Antonio Rovira, ja s’ha gastat més de 10.000€ dels nostres impostos en dinars i sopars',
  ogDescription: 'Destapem que el el pitjor Conseller d’Educació de la història, José Antonio Rovira, ja s’ha gastat més de 10.000€ dels nostres impostos en dinars i sopars',
  ogImage: 'https://roviraleaks.compromis.net/images/ogimage.png',
  twitterCard: 'summary_large_image',
})
</script>

<template>
  <main>
    <SiteHeader>
      <SiteTitle />
    </SiteHeader>
    <div class="container">
      <section class="text text-intro">
        <h1 v-motion-fade-visible class="visually-hidden">
          RoviraLeaks
        </h1>

        <Languages v-motion-slide-visible-bottom :delay="100" />

        <div v-motion-slide-visible-bottom :delay="200">
          <p>El pitjor Conseller d’Educació de la història, José Antonio Rovira, ja s’ha gastat més de <Annotated type="highlight" inmediate>10.000€ dels nostres impostos en dinars i sopars</Annotated>. Convidant a persones que no sabem qui son en bars, restaurants, i marisqueries. Mentrestant, alguns professors han de pagar el material escolar de la seua butxaca.</p>
          <p>Sense publicar les factures al portal de transparència. Sense que consten reunions en l’agenda oficial. <Annotated>I tot això mentres cobra un sou de 85.000€ anuals</Annotated>.</p>
          <p><Annotated type="highlight">PP i Vox volen canviar la llei per a amagar esta informació</Annotated>. Per això des de Compromís fem públics els <Annotated>70 tickets</Annotated> que demostren com els amics de Mazón utilitzen la Generalitat com el seu caixer automàtic en lloc de millorar la vida dels valencians i valencianes.</p>
        </div>
      </section>
    </div>
    <Invoices />
    <Share>
      <template #title>Fes-ne difusió!</template>
      <p>Comparteix aquesta pàgina amb les teues amistats.</p>
    </Share>
  </main>
</template>
