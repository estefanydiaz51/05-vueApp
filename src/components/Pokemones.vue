<template>
    <div>
        {{ pokemones }}
    </div>
</template>
<script>
import { ref } from '@vue/reactivity'
    export default {
        async setup() {
            const pokemones = ref([]);

            try {
                const res = await fetch('https://pokeapi.co/api/v2/pokemon')
                pokemones.value = await res.json()
            }catch ( error ) {
                console.log( error )
            }
            // const solicitarApi = async () => {
               
            // }

            // solicitarApi()

            return { pokemones }
        }
    }
    
</script>