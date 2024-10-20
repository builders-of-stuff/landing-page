<script lang="ts">
  import * as PageHeader from '$lib/components/docs/page-header/index.js';
  import {
    // SiteFooter,
    SiteHeader
    // TailwindIndicator
  } from '$lib/components/docs/index.js';
  import { CardsNewYork } from '$lib/registry/new-york/example/cards/index.js';
</script>

<SiteHeader />

<div class="container">
  <div class="relative flex flex-col items-start md:flex-row md:items-center">
    <PageHeader.Root>
      <PageHeader.Heading class="md:block">Builders of stuff</PageHeader.Heading>
      <!-- <PageHeader.Description balanced={false}>
        (under construction)
      </PageHeader.Description> -->
    </PageHeader.Root>
  </div>
  <CardsNewYork />
</div>
