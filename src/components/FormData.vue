<template>
    <form @submit.prevent="enviarDatos">
        <input type="text" name="" v-model="nombre" placeholder="Nombre">
        <input type="number" name="" v-model="edad" placeholder="Edad">
        <div>
            <input type="checkbox" v-model="cursos" value="html">
            Html
            <input type="checkbox" v-model="cursos" value="css">
            Css
            <input type="checkbox" v-model="cursos" value="js">
            Js

        </div>
        <div>
            <input type="radio" v-model="nacionalidad" value="México">
            México
            <input type="radio" v-model="nacionalidad" value="Argentina">
            Argentina
            <input type="radio" v-model="nacionalidad" value="España">
            España
        </div>
        <button type="submit">Enviar</button>
    </form>
    <pre>{{ user }}</pre>
    <pre>{{ arrayDatos }}</pre>
</template>

<script setup>
const { reactive, ref, toRefs }=require("@vue/reactivity");

    const user = reactive({
        nombre: '',
        edad: 0,
        cursos: [],
        nacionalidad: ''
    })
    const arrayDatos = ref([]);

    const { nombre, edad, cursos, nacionalidad } = toRefs(user);

    const enviarDatos = () => {
        if ( !nombre.value.trim() ) {
            console.log( 'nombre vacio' );
            return;
        }
        // const copy = {...user }
        arrayDatos.value.push( {
            nombre: nombre.value,
            edad: edad.value,
            cursos: cursos.value,
            nacionalidad: nacionalidad.value

        } );

        nombre.value = '';
        edad.value = 0;
        cursor.value = [];
        nacionalidad.value ='';
    }
</script>