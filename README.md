# Shockinflux Payview Component for Vue 2.x

A Vue Plugin for Shockinflux-Payview Payment Gateway.

### Demo

![Demo Image](shockinflux-demo.png?raw=true "Demo Image")

### Install

##### NPM

```
npm install vue vue-shockinflux-payview --save
```

##### via CDN

```javascript
<!-- Vue -->
<script src="https://unpkg.com/vue/dist/vue.js"></script>

<!-- Vue-shockinflux-payview -->
<script src="https://unpkg.com/vue-shockinflux-payview@1.0.0/dist/shockinflux.min.js"></script>

```

### Usage


##### Via NPM/ Vue-cli
[Usage Example via NPM or Yarn](examples/commonjs/App.vue)

###### shockinflux-payview.vue

```vue
<template>
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
                style-class="shockinflux-inline-btn"
                :close="close"
    ><i>Pay Now!</i></ShockinfluxPayview>
</template>
<script type="text/javascript">
import ShockinfluxPayview from "vue-shockinflux-payview";
export default {
  components: {
    ShockinfluxPayview
  },
  data() {
    return {
          email: "foobar@example.com",
          amount: 10000,
          transactionid: "836327236732632671009",
          storeid: "g1xq8y87************9XBJbKXuZo+x3uqw=",
          comment: "This is a test",
    };
  },
  methods: {
    callback: function(response) {
      console.log(response);
    },
    close: function() {
      console.log("Payment closed");
    }
  }
};
</script>
<style>
.shockinflux-inline-btn {
  color: #04193d;
  width: 250px;
  height: 50px;
  font-weight: 800;
}
</style>
```

#### via CDN
[Usage Example via CDN](examples/index.html)

```javascript
new Vue({
  el: "#app",
  components: {
    ShockinfluxPayview: ShockinfluxPayview.default
  },
  methods: {
    callback: function(response) {
      console.log(response);
    },
    close: function() {
      console.log("Payment canceled");
    }
  },
  data: {
      email: "foobar@example.com",
      amount: 10000,
      transactionid: "836327236732632671009",
      storeid: "g1xq8y87************9XBJbKXuZo+x3uqw=",
      comment: "This is a test",
  }
});
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Some commit message'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request 😋

Don't forget to give me a star and [follow me on twitter](https://twitter.com/temitopedaviid)!

Thanks!
Adesoji Temitope.

## License

This project is licensed under the MIT License - see [LICENSE.md](LICENSE.md)
