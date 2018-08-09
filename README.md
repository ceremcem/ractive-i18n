# Ractive Translation
This HOWTO describes the proper translation approach in Ractive.

## Requirements 

- [x] Shouldn't be verbose
- [x] Should be available in template 
- [x] Should be available in script side with the same name 
- [x] Should be lazily loadable/upgradable
- [x] Should let existing strings converted to "multi language strings" with a minimum amount of overhead
    
    > Just encapsulate the string in `i18n("...")` function
    
- [ ] Should be able to be applied to third party libraries. 
- [ ] Should be able to let every component define its own translation in the component file.
- [ ] Should let changing sentence structure 

## Proposed Method

Use a global `i18n()` function: [Playground (WIP)](https://ractive.js.org/playground/?file=index.ractive.html#N4IgLiBcIgNCBnKN4GNlxACyqATlAHYCuANqfEpANogD0dqAJoQHQBWCTApqQJYA3PK0LcwdQgAcAtnTwBDVGEHcAAtyYBzbnMXKB3DggD8ARhABdAL7xpUU-ABmVaqELzp3ZH0I8AHqwKSiqsWGDSpJioAPaEYNxxyAA8CLzcSgAEAvKkxNwAvAA6IMDAqghY8ngarHymABxspPKEmlZWxRmxALSola0FxeWV1Uy1DU3R8kwAFKqE0Tys2bncAJTFAHyFhBkZSdGSyrFZOXlFJcDEvtyOPhrtWzMAIrfyZGBrSXSHx4Tbu32vz4sU2pgAzOCAOzfYGgnZ7A5HEH-ABi0Tw0hysOR8MBSL+mwAavJNHkcYSdt9UqR0mAAVSsKZNgAJXikaKwfYISQtTalOqNGbuTwZAA+YoyAHIAEp6FRStbtam8-4AQm+TIBSQARsQwGATj1UPxUABrC4IeQATzZ5GiWwFExmUqt1oyWHZ0UVyroeoNeKpCFQeD4RwBez40kkGLAGUFhAACrlND4Mo48NFpNLWHQE0YpQBuBEZEsxQgIOMAQUkkgy+QycuCBlY3D88V8M2AJb2xFSkAy1ATyeIqcIMzWFlgPYy8WjzXiA4AJAAVACiAFlEwAZKvr6eAvaoBAIZcAYQAyheD3sjyeAJJMAdS+S1qU32+xAfdw+3nx8MAB0ca5gliGYlD8NYf1vGCMgYWdogyHVuAyeQdVpBCMj7FCKljLJuDwBAUVQuMACkLwyIieFLX8YIAdx8Jhojo8ZGnrWcsD4BBQl4SQCO4hNi1ojIbBnQowFdG07Q5KUgJAv5wLASDoNgvYcgIsAZgTF03Q9L1FQ2QhxL2cSOkBUySysNYhLLWJK1Q2t2IY3xmNYV86wbUQ6IyGtJC7GcwCqbRAOlHVFmtKVLOsqk6GDUNwx2IMwGtWkIw9UwMmADIYg5PABwAYgABkK+oGnkQsRJiysUu4AEQBsNwPC8aB804KJYg7CBoFpOMOWmDR2McHJUhs0Q-BjPA4x4IaPnTeTiMkFMfBmX4EDWTLErAaowGIPBdmAwhQPHLKm30bguR8SsWlQFCrI239LsCw7DE9Ug+MI6gVqOBBxUlYArJEJrfulBMpQsdiZkrPB1vyTZ7tU8t7OaVp2NOkIKiqDQAHExBdfNkc0RUhIRuy4yxDzG3lFsMdGHHNIAA3zcnWCXYACasenouEvhHAyGZyYyAAyQXKK2+NdnJ9btt2iXX2oKGLGJ2DeFSeHVPjXn+dfIWRbRltnjXAAhABVLH1sR6JaVYOiqnHemADlEK2loEAXYj5GyPhmnQlDHAxaVWahqwpXFjJWfZzmldU6W9tFvAo9vMyYLMmceb5tU+p4Jh1pUmDM4GhstryBPxL1wwaY0C9calfGpiYd8MgJ+s4dz2DEbJ7WGzL1gK6YOmZkZiZWGZ8OWjaSOZxgtOZjVSW1fVjW+ab-IV+lCFoUVSnm3LkZK9xwfGmH18WbZseOa5LLJ-V2Uqe4WTpRlAAWVAoVMIk74-Be9kk91Xpk58ECP1-uCcghVIrCWTlzL+GQVYoWnsvVeUp0SYhyJvVIYAVxRm4NEfUMwJzNy3mdHuu8mBVwZkzY+o9Wjn0yjRaB38y73ylBePgeBCEKivpArk4JiqFSgV-WBi8ZgIIbFKEkZI77rXQZgzwODNL4Nhuw6mJCyEDwoZIE+EcL50PoTfbeTCy7dC4lgcB0CrJclMLw-hqkk63lMtYyqgIrBCSsPVKcIBbjeBuAEIIRCwgRHqkAA)

~~**Restrictions**: Can not update its output when language is changed.~~ [Resolved by @evs-chris](https://gitter.im/ractivejs/ractive?at=5b6c967a179f842c9716dd1d)


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

### Translation Table 
| en | tr |
| --- | --- |
| hello world | merhaba dünya | 
| Button at index 1 says hello | 1 Numaralı düğme merhaba diyor | 

## Related Conversations 

* [06.07.2018...](https://gitter.im/ractivejs/ractive?at=5b3f946633b0282df405e475)
* [09.08.2018...](https://gitter.im/ractivejs/ractive?at=5b6c1487179f842c9713abc4)

