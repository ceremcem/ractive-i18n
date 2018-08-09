# Ractive Translation
This HOWTO describes the proper translation approach in Ractive.

## Requirements 

- [ ] Shouldn't be verbose
- [ ] Should be available in template 
- [ ] Should be available in script side 
- [ ] Should be lazily loadable/upgradable
- [ ] Should let existing strings converted to "multi language strings" with a minimum amount of overhead
- [ ] Should be able to be applied to third party libraries. 

## Proposals

* Global Function 
Use a global function (something like `_t()`) which will look at a dictionary an get corresponding translation.

**Restrictions**: Can not update its output when language is changed. 


## Related Conversations 

* [06.07.2018...](https://gitter.im/ractivejs/ractive?at=5b3f946633b0282df405e475)
* [09.08.2018...](https://gitter.im/ractivejs/ractive?at=5b6c1487179f842c9713abc4)

