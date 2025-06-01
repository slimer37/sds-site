<script lang="ts">
    import { page } from '$app/state';
</script>

<div class='central'>
    <h1>{page.status}</h1>
    <h2>{page.error!.message}</h2>
</div>

<style>
    .central {
        display: flex;
        flex-direction: column;
        justify-content: center;
        width: 100%;
        height: 100%;
        text-align: center; 
    }
</style>