# Recursividad - Torres de hanoi

```js
const hanoi = (nDiscos, origen, destino, auxiliar) => {
    let disco = null;
    if (nDiscos == 1) {
        // movemos origen a destino
    } else {
        hanoi(nDiscos - 1, origen, auxiliar, destino);
        // movemos origen a destino
        hanoi(nDiscos - 1, auxiliar, destino, origen);
    }
}

hanoi(3, torreOrigen, torreDestino, torreAuxiliar);
```

> Paso a paso

movimientos = 0

- hanoi(3, origen, destino, auxiliar);
    - hanoi(2, origen, auxiliar, destino);
      - hanoi(1, origen, destino, auxiliar);
        - Se mueve el disco de origen a destino [movimientos++] 1
      - Se mueve el disco de origen a auxiliar [movimientos++] 2
      - hanoi(1, destino, auxiliar, origen);
        - Se mueve el disco de destino a auxiliar [movimientos++] 3
    - Se mueve el disco de origen a destino [movimientos++] 4
    - hanoi(2, auxiliar, destino, origen)
      - hanoi(1, auxiliar, origen, destino)
        - Se mueve el disco de auxiliar a origen [movimientos++] 5
      - Se mueve el disco de auxiliar a destino [movimientos++] 6
      - hanoi(1, origen, destino, auxiliar)
        - Se mueve el disco de origen a destino [movimientos++] 7

7 Movimientos
