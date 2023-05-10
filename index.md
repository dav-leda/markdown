

# CSS en Vue.js

Una de las ventajas de Vue.js es la facilidad con la que se pueden aplicar clases de CSS a elementos HTML en forma dinámica, es decir, de acuerdo a cómo van cambiando los datos de la aplicación.

Por ejemplo, tenemos una tabla con una lista de alumnos y queremos que al cliquear sobre el nombre la propiedad `alumno.presente` pase de `false` a `true` (o viceversa), y que además, el color de fondo de esa fila pase a ser verde:


El color de fondo cambia porque le estamos indicando a Vue que, cuando esa propiedad cambia, que le agregue a esa fila la clase de CSS `'fondo-verde'`.

Y, ¿cómo cambiamos las clases de CSS de acuerdo a los datos? De varias maneras. Vue es tan flexible en este punto que hasta resulta confuso por la variedad de formas en que se puede hacer.

Veamos una por una:

## Clase simple

Esta es la forma más fácil de hacerlo, pero sólo puede ser usada cuando el dato y la clase de CSS tienen el mismo nombre. 

Por ejemplo, en `data` tengo una propiedad llamada `rojo` y en `<style>` tengo una clase de CSS también llamada `rojo`.

Entoces, al elmento de HTML que quiero que cambie de color le agrego el atributo `v-bind:class` (o sea, una clase dinámica, que cambia de acuerdo al dato que se le pase), o en forma abreviada: `:class`.

```html
<template>

  <h2 :class="{ rojo }" @click="cambiarColor"> CLASE SIMPLE </h2>

</template>

<script>

export default {

  data: () => ({
    rojo: false
  }),

  methods: {
    cambiarColor() {
      this.rojo = !this.rojo
    }
  }
}
</script>
```



