---
title: Typesript Notes
layout: default
---
  
| Code | Result |
| - | - |

```
class Cat {
  private name: string; 
  private color: string; 
  constructor(name, color) { this.name = name;  this.color = color;}
}
```
same as
```
class Cat {
    constructor(private name, private color) {}
    }
```

usage
```
let fluffy = new Cat('fluffy', 'White')
```


