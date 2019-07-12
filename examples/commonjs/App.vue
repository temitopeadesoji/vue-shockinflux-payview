<template>
    <div class="main">
            <ShockinfluxPayview
                :email="email"
                :amount="amount"
                currency="ngn"
                template="modern"
                language="en"
                action="float"
                :transactionid="transactionid"
                :storeid="storeid"
                :comment="comment"
                :callback="callback"
                style-class="paymentbtn"
                :close="close"
            ><i>Pay Now!</i></ShockinfluxPayview>
    </div>
</template>

<script type="text/javascript">
import ShockinfluxPayview from '../../src';
export default {
    components: {
        ShockinfluxPayview
    },
    data(){
        return{
          email: "foobar@example.com",
          amount: 10000,
          transactionid: "836327236732632671009",
          storeid: "g1xq8y87y800000U2FsdGVkX1/LaykxunCYjDqjtawGReF+0CLekeY8v7YNA3U4jjYZo4OMehhOt5WpudyuTJYG2AACiy/JNw1IhlfCFVYDF3B7Hu0AHU4qOsLiAh15Kkal7dF8zi7Sb0g9HHhXo7q4X3FYeRERDjGqnCa0gOBmcjyn/niZtvb01Rtt5Ugcg5CUpIAWmZShwKgLyerrG1vrwuSqEischxDKapM5avW9XBJbKXuZo+x3uqw=",
          comment: "This is a test",
        }
    },
    methods: {
      callback: function(response){
        console.log(response)
      },
      close: function(){
        console.log("Payment canceled")
      }
    }
}
</script>
<style>
    .main {
        text-align: center;
    }
    .shockinflux-inline-btn{
        color: #04193d;
        width: 250px;
        height: 50px;
        font-weight: 800;
    }
</style>
