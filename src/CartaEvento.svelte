<script lang="ts">
   interface Evento {
        titulo: string;
    descripcion: string;
    startYear: number;
    endYear?: number;
    }

    export let style: string = '';
    export let datos:Evento = {titulo: '', descripcion: '', startYear: 1000}; 
</script>

<div class="evento" style={style}>
    <div class="title-block">
        <h1>{datos.titulo}</h1>
        <h2>{datos.startYear}</h2>
    </div>
    <p>{datos.descripcion}</p>
</div>

<style lang="scss">
    .evento {
        padding: 24px;
        min-width: 200px;
        border: solid teal 2px;
        border-radius: 12px;

        text-align: left;
    }

    .title-block {
        display: flex;
        align-items: center;
    }
    
    h1 {
        flex-grow: 1;
    }

    h2 {
        flex-grow: 0;
    }
</style>