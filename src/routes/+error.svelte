<script lang="ts">
    import { page } from '$app/state';
</script>

<div class="max bg-dino"></div>
<div class="max">
    <div class='central'>
        <h1>{page.status}</h1>
        <h2>{page.error!.message}</h2>
    </div>
</div>

<style>
    .bg-dino {
        background-image: url('dino.svg');
        background-repeat: no-repeat;
        background-position: center;
        background-size: 20em;

        filter: contrast(0);
    }

    .max {
        display: flex;
        align-items: center;
        justify-content: center;

        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        left: 0;
    }

    .central {
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: center; 

        padding-bottom: 40px;
    }
    
    h1 {
        font-size: 5em;
    }

    h2 {
        font-size: 1.5em;
    }
</style>