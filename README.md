

# Vue.js Warehouse

A Cross-browser storage for **Vue.js** and **Nuxt.js**

This plugin will **pick the best available browser storage**, and automatically **falls back to the first available** storage that works.



## Features

* Backed by the great library [Store.js][storejs]
* Support for multiple Storages (localStorage, cookies, etc.)
* Basic key/value storage functionality (`get/set/remove/each`)
* Easy integration with Vue.js
* Support for Nuxt.js
* Get notified with Vuex when the stored values change



## Installation

This module is distributed via [npm][npm-homepage] which is bundled with [node][node-homepage] and should be installed as one of your project's `dependencies`:

```bash
npm install --save store vue-warehouse
```

or

```bash
yarn add store vue-warehouse
```

## Example of use

Suppose you want to use **localStorage** by default and **cookies** as an alternative in case your user's browser doesn't allow any interaction with **localStorage** (Safari Private mode). Besides, you want to define **defaults values** and an **expiration date** for all the data that is going to be saved.

### Configuration for Vue.js

```javascript
import Vue from 'vue'
import VueWarehouse from 'vue-warehouse'
import VueWarehouseSync from 'vue-warehouse/sync'

import VuexStore from './vuex/store' // vuex store instance
import VueWarehouseStore from 'store' // vue-warehouse store instance

VueWarehouseSync(VuexStore, VueWarehouseStore)

Vue.use(VueWarehouse, {
  store: VueWarehouseStore,
  plugins: [
    require('store/plugins/expire'),   // Expire stored values at a given time
    require('store/plugins/defaults')  // Declare default values
  ],
  storages: [
    require('store/storages/localStorage'),  // localStorage support
    require('store/storages/cookieStorage')  // cookies support
  ]
})
```

### Configuration for Nuxt.js

```javascript
{
  modules: [
    ['vue-warehouse/nuxt',
      {
        vuex: true,
        plugins: [
          'store/plugins/expire',
          'store/plugins/defaults'
        ],
        storages: [
          'store/storages/localStorage',
          'store/storages/cookieStorage'
        ]
      }
    ],
  ]
}
```

### API Usage

```javascript
// Define defaults values
this.$warehouse.defaults({ user: { name: 'John Doe' } })

// Change current user with an expiration date of 2 hours starting from now
const expiration = new Date().getTime() + (3600 * 2000)
this.$warehouse.set('user', { name:'Marie Doe' }, expiration)

// Get current user value
this.$warehouse.get('user')

// Get current user expiration
this.$warehouse.getExpiration('user')

// Remove current user
this.$warehouse.remove('user') // return the default value -> { name: 'John Doe' }

// Clear all keys
this.$warehouse.clearAll()

// Loop over all stored values
this.$warehouse.each(function(value, key) {
	console.log(key, '==', value)
})
```

### Vuex State

The last change made to the **browser store** (localStorage, cookie, etc.) are synced with the Vuex state:

```javascript
// Store current user
this.$warehouse.set('user', { name: 'John Doe' })

// Update the user
this.$warehouse.set('user', { name: 'Marie Doe' })

// get state values
store.state.warehouse.action    // action performed -> set
store.state.warehouse.key       // key affected     -> user
store.state.warehouse.value     // stored value     -> { name: 'Marie Doe' }
store.state.warehouse.oldValue  // last value       -> { name: 'John Doe' }
```
s

## Contributing

Please make sure to read the [Contributing Guide][contributing] before making a pull request.

## Code of Conduct

Everyone participating in this project is expected to agree to abide by the [Code of Conduct][code-of-conduct].

## License
