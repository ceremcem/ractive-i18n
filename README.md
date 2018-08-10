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

Use a global `i18n()` plugin: [Playground (WIP)](https://ractive.js.org/playground/#N4IgLiBcIgNCBnKN4GNlxACyqATsgDYCGYApghPEpANoC6AvvALZQCM8AZjbaAHbEWZZAEt+AEzIAPAHR5iqMKIBuZWVjAtCmVAHt+5Q8gA8CMoTJKABCuKEArmQC8AHRDBgAAQRZieMglZUXYADn5ZEn4Ac0ZGd2sDAFpUPxiXdx8-AKCQ8Mi9YgkACi9+PSlZO0cyAEp3AD5XfmtrEz0AB2UDW3snNw9gB0kyLnFAuMbigBFR4gdCMFqTAHpO7v4mlrb10QMG9gBmQ4B2Vd395tb2rr3NgDE9PBZ7c9vL7ZuNhoA1YminG9vs1VuZLEotiCsOwGgAJCyEPSwNoIDrETaeMDFQTCawAHzx1gA5AAlRTKNRE2pxUFozYAQlW0K2JgARg4wGAeslUIRRKgANYDBDEACe8MIiMamOKRJFousWAReipNJW7M5HxBCFQeFEXS2rVELA6TzA1jy-AACo5ouJrFw8HoWMTZCtLbIAFYIIkAbiu1gD+n4lGsAEEOh1rM5rGSlKp1DIjCVgAHWg5zJBrLRLTaHHb+MVgNZoojWfYs2A8E5kTiyFmiWAidZGLV6LA09ZyCaSOQswASAAqAFEALJWgAyYZHHe2rVQCAQA4AwgBlVez1rzxcASQkDeIkaJm63Bizqbngab8oliKJWa4w3jBmKSmktQvW6-1nsZDwWKxOUxUVZUqXqfhXHNK94m2SCYNaVt-Qg7Zg1DQ8oxjAB3cQJD0TDZHQ6NrH4MhMPDSMi07MB-GiMgwAbVkKlFIkA0QkEVh1PUDWabUwFFSxDUVdhrGLfRETwLMAGIAAZpNCMJiF9Ft2MofiyC2EBmAEIQRGgD1vV0AwjAgaBLHNREikCIiuHscwkOaGRTX-awpBshZzUffhnxaDpbXEYoLhDWoRKDAxQ3WBAiMCyKCRExh7KrOiHDwFpPO8otY3JBNkXESh0VQMgW2Cz8t1QjyWhjYpKDwYLnAaELL3nMLzPRaIiLjCl1F8fxAgAcTo2UPSiaIqSQ79rDK6wXgwzL4zUWRupyfqsQAAw9abZH7YBhsYFbajG79RC4aximm6wADJzusaqLRaabgoCMBkruw9aGq+gDq-CxzAa8ajWO07Dwuq6OoTWRpmHAAhABVXrgtQvRLFkTD-ELFaADk9C7BQQ17O4fzsUQSFZSwHSeYktuqxhm3tLadr2z7v0e57rqrRmEM7eLO07XLqK89QlUIDo-wQWgItkOt8UJIlLSJehrP4ezLyOk76QsqQJGKztWnVqyYyrJxGcg0H5sWwJVwGmWwgidXj2sYbo3qkrxsms6YxNrrsj6ga1ut2QNrp1rdv27WtxV4p6Xu36-v+k6HecBPiSOU4qVmzqFq9iQLdW9bD027ag5W5Fi1D8bSSyykGxJAAWVATnYH4yGPUvvyAhVBbvBsEGr9vDklaSWMa782KHr7CB+8P48TolHmeexU-MMBB2NMg9A5Ypilq+qPYznqs593OOnz+ni8DUfW49+9iVXUQ8DThNB5jhDamRQ5ZOkkPz9ab7Csn1ro2nn8AETdgqL2XsINeWJN6O3vqbTO2dii+3yAHAuMRdqnxbl+cuc0m5VwrmQJIohfCPyfq2ZE7B36fxjvBLccEqFbhgjzAG4tSx6HLIQLWl5IKTTIPwFQRE+LCz0MdbCkg8LWHpNPYYrlxgSGbAAfmsKI3CZFKyiiEcdVh7CJFSJGGMEicjrCKK0fYaw54uZD3DvSDe4tJaxStuEVO9peEqFqMFFxYsugIAljpKWxJZbyxjFwRWnNWJIUYJpdsIBRhiBGHIBQOCNBaB0IwIAA)

~~**Restrictions**: Can not update its output when language is changed.~~ [Resolved by @evs-chris](https://gitter.im/ractivejs/ractive?at=5b6c967a179f842c9716dd1d)


## Test Application 

A successfull approach should be able to convert [the following application](https://ractive.js.org/playground/?env=docs#N4IgFiBcoE5SAbAhgFwKYGcUgL4BoQN4AdAO1LQHcACAJSQGMUBLANzQApgzrq0FI1AOQAjAPYATAJ5C8PaugC2AB2TpBAA3m8APGIQA+bb2rBgAYjSMw1AIIwYSKRwDMAShw5jJ6joTMjUh9g3xEAVxQUMSDogFoGfwYAawBeYkInAAl+BDF0gzAcsWpKMRgECR0AenDI6MCQ3Sr-BuCzKqsGME8yYhQ+6v1Avo05IOpowW5x3gwsosEAMzDSJmZojiYADzdpkNYkGGpmahTqbYA6AHM0FA4hAAFmUgk0LaE3agBqagBGAG5eN5qEgEGgYHchAAhCJRIKoY4vN7Cb7HVFCahzKQYaiFBC5D7GLzjYk4NwgAjYSAgHQSNjHCRpEDmJDKZT5ap01gGXBAA) into a multi language app with minimum effort: 

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
| en/default | tr |
| --- | --- |
| hello world | merhaba dünya | 
| Button at index 1 says hello | 1 Numaralı düğme merhaba diyor | 

## Related Conversations 

* [06.07.2018...](https://gitter.im/ractivejs/ractive?at=5b3f946633b0282df405e475)
* [09.08.2018...](https://gitter.im/ractivejs/ractive?at=5b6c1487179f842c9713abc4)

