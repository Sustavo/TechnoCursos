<template>
    <header>
        <nav>
            <div class="logo">
                <router-link to="/">Techno</router-link>
            </div>
            <ul>
                <li>
                    <router-link to="/cursos">Cursos</router-link>
                </li>
                <li>
                    <router-link to="/Contato">Contato</router-link>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
     name:"TheHeader",
}
</script>

<style scoped> 
header {
    background: #234;
}

header a {
    color: white;
}

a.router-link-exact-active {
    color: #4B8;
  }

nav {
    max-width: 800px;
    margin: 0 auto;
    display: flex;
    align-content: space-between;
    padding: 20px;
}

.logo {
    flex: 1;
}

.logo a {
    font-size: 2rem;
    color: white;
}

ul li {
    display: inline-block;
}

li a {
    padding: 0 10px;
    margin-left: 10px;
}
</style>