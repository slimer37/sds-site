<script lang="ts">
    import { page } from '$app/state';
</script>

<div class="max">
    <div class='central'>
        <h1>{page.status}</h1>
        <h2>{page.error!.message}</h2>
    </div>
</div>

<style>
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
    }
</style>