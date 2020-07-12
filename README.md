# Trampolin de Recursividad en Javascript

### Evita el error _maximum call stack size exceeded_.

> Para utilizarlo debemos asegurarnos que devolvemos una función en cada iteración.

**No Funciona**
```javascript
const op = (n, acc = 0) => {
    n === 0 ? acc : op(n - 1, acc + n)
}
```

**Funciona**
```javascript
const op = (n, acc = 0) => {
    n === 0 ? acc : () => op(n - 1, acc + n)
}
```

**Para Usarlo**
```javascript
const tOp = trampolin(op);
const resultado = tOp(50000);
```
