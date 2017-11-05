<template lang="pug">
.row
  secondary-menu.col-12
    router-link.nav-link(:to="{name: 'site'}", exact, :class="{'active': $route.name === 'site'}") {{ $t('site') }}
    router-link.nav-link(:to="{name: 'api'}", :class="{'active': $route.name === 'api'}") {{ $t('API') }}
    router-link.nav-link(:to="{name: 'awsIoT'}", :class="{'active': $route.name === 'awsIoT'}") AWSIoT
    router-link.nav-link(:to="{name: 'dataExport'}", :class="{'active': $route.name === 'dataExport'}") {{ $t('dataExport') }}
  .col-12
    router-view
</template>

<script>
import SecondaryMenu from 'client/components/secondaryMenu';

export default {
  components: {
    SecondaryMenu,
  },
};
</script>
