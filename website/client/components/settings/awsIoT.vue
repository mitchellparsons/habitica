<template lang="pug">
.row.standard-page
  .col-6
    h2 AWSIoT
    p "A Paragraph"
      h4 acp7yis5xraca.iot.us-west-2.amazonaws.com
      a(href="https://www.symantec.com/content/en/us/enterprise/verisign/roots/VeriSign-Class%203-Public-Primary-Certification-Authority-G5.pem") Root CA
    button.btn.btn-sm.btn-primary(type='submit', @click='createCertificate()') Create IoT Certificate
    
    
    .section
      h3 Certificate pem
      textarea(v-model='certificatePem')
    
    .section
      h3 Private Key
      textarea(v-model='privateKey')

</template>

<style scoped>
  .section {
    margin-top: 2em;
  }
</style>

<script>
export default {
  data () {
    return {
      certificatePem: '',
      privateKey: '',
    };
  },
  methods: {
    async createCertificate () {
      let keysAndCert = await this.$store.dispatch('user:createAWSIoTCertificate');
      this.certificatePem = keysAndCert.certificatePem;
      this.privateKey = keysAndCert.privateKey;
    },
  },
};
</script>
