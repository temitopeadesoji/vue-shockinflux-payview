<template>
  <button
    class="shockinflux-inline-btn"
    @click="payWithShockinflux"
  >
    <slot>Make Payment</slot>
  </button>
</template>

<script type="text/javascript">
export default {
    props: {
        styleClass: {
            type: String,
            default: 'payButton'
        },
        email: {
            type: String,
            required: true
        },
        amount: {
            type: Number,
            required: true
        },
        currency: {
            type: String,
            default: 'ngn'
        },
        template: {
            type: String,
            default: 'modern'
        },
        language: {
            type: String,
            default: 'en'
        },
        action: {
            type: String,
            default: 'float'
        },
        transactionid: {
            type: String,
            required: true
        },
        storeid: {
            type: String,
            required: true
        },
        comment: {
            type: String,
            required: true
        },
        callback: {
            type: Function,
            required: true,
            default: (response) => {}
        },
        close: {
            type: Function,
            required: true,
            default: () => {}
        },
        country: {
            type: String,
            default: 'ng'
        }
    },
    created() {
        const script = document.createElement('script')
        script.src = 'https://scripts-cdn.boxedall.com/shockinflux/v2/payview/js/shockpaymentv2_client.js'
        document.getElementsByTagName('head')[0].appendChild(script)
    },
    methods: {
        payWithShockinflux() {
            // console.log(this.transactionid)
            window.shock_payview({
                'email': this.email,
                'amount': this.amount,
                'currency': this.currency,
                'template': this.template,
                'language': this.language,
                'action': this.action,
                'transactionid': this.transactionid,
                'storeid': this.storeid,
                'comment': this.comment,
                onclose: () => this.close(),
                "callback": response => this.callback(response)
            })
        }
    }
}
</script>
<style>
    .shockinflux-inline-btn{
        color: #61DAFB;
        width: 250px;
        height: 50px;
        font-weight: 800;
    }
</style>
