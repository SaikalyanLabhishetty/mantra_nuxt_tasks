<template>
    <div>
        <header>
            <nav>
                <ul class="header">
                    <li><NuxtLink id="link" to="/movies">Movies</NuxtLink></li>
                </ul>
            </nav>
        </header>
       <div>
        <slot/>
       </div>

       <footer>
        <ul class="header">
                    <li><NuxtLink id="link" to="/">Home</NuxtLink></li>
                    <li><NuxtLink id="link" to="/movies">Movies</NuxtLink></li>
                </ul>
       </footer>
    </div>
</template>

<style scoped>
.header{
    display: flex;
    flex-direction: row;
    gap: 50px;
    justify-content: center;
}
li{
    list-style: none;
}
#link{
    text-decoration: none;
    color: white;
    font-weight: bold;
    font-size: 24px;
}
</style>