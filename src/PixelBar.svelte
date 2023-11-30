<script>
    export let a = 100;
    export let b = 50;
</script>

<div class="bar">
    <div class="inner-bar" style="height: {a}px"></div>
    <div class="inner-bar" class:red={true} style="height: {b}px"></div>
</div>

<style>
    .bar {
        margin: auto;
        width: 5px;
        border-radius: 3px;
        background-color: red;
    }
    .inner-bar {
        width: 1px;
        background-color: black;
        border-left: 3px solid white;
        border-right: 3px solid white;
        border-top: 1px solid black;
    }
    .inner-bar:last-child {
        border-bottom: 1px solid black;
    }
    .red {
        background-color: red;
    }
</style>
