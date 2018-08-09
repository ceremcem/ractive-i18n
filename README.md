# Ractive Translation
This HOWTO describes the proper translation approach in Ractive.

## Requirements 

- [ ] Shouldn't be verbose
- [ ] Should be available in template 
- [ ] Should be available in script side 
- [ ] Should be lazily loadable/upgradable
- [ ] Should let existing strings converted to "multi language strings" with a minimum amount of overhead
- [ ] Should be able to be applied to third party libraries. 
- [ ] Should be able to let every component define its own translation in the component file.
- [ ] Should let changing sentence structure 

## Proposals

* Global Function 
Use a global function (something like `_t()`) which will look at a dictionary an get corresponding translation.

**Restrictions**: Can not update its output when language is changed. 


## Test Application 

A successfull approach should convert [the following application](https://ractive.js.org/playground/?env=docs#N4IgFiBcoE5SAbAhgFwKYGcUgL4BoQN4AdAO1LQHcACAJSQGMUBLANzQApgzrq0FI1AOQAjAPYATAJ5C8PaugC2AB2TpBAA3m8APGIQA+bb2rBgAYjSMw1AIIwYSKRwDMAShw5jJ6joTMjUh9g3xEAVxQUMSDogFoGfwYAawBeYkInAAl+BDF0gzAcsWpKMRgECR0AenDI6MCQ3Sr-BuCzKqsGME8yYhQ+6v1Avo05IOpowW5x3gwsosEAMzDSJmZojiYADzdpkNYkGGpmahTqbYA6AHM0FA4hAAFmUgk0LaE3agBqagBGAG5eN5qEgEGgYHchAAhCJRIKoY4vN7Cb7HVFCahzKQYaiFBC5D7GLzjYk4NwgAjYSAgHQSNjHCRpEDmJDKZT5ap01gGXBAA) with minimum effort: 

```js

new Ractive({
  el: 'body',
  template: `
    <ol>
      {{#each Array(3)}}
        <li>
          <button on-click="sayHello">hello world</button>
        </li>
      {{/each}}
		</ol>
	`,
  on: {
    sayHello: function(ctx){
      var i = ctx.get('@index') + 1;  
      alert('Button at index ' + i + ' says hello')
    }
  }
})
```

## Related Conversations 

* [06.07.2018...](https://gitter.im/ractivejs/ractive?at=5b3f946633b0282df405e475)
* [09.08.2018...](https://gitter.im/ractivejs/ractive?at=5b6c1487179f842c9713abc4)

