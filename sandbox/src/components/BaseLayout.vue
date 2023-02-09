<script>
export default {}
</script>

<template>
    <div class="wrapper">
        <aside class="sidebar">
            <slot name="sidebar" />
        </aside>
        <main class="main">
            <slot name="main" />
        </main>
    </div>
    <footer class="footer">
        <slot name="footer" />
    </footer>

</template>

<style>
.sidebar {
    border: solid 2px red;
}
.main {
    border: solid 2px green;
}
.footer {
    border: solid 2px blue;
}
</style>