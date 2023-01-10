<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
        <div v-if="loading">
            <PageLoading />
        </div>
        <transition>
            <div v-if="api">
                <h1>{{ api.titulo }}</h1>
                <p>{{ api.descricao }}</p>
                <ul class="cursos-lista">
                    <li v-for="curso in api.cursos" :key="curso.id">
                        <h2>
                            <router-link :to="{name: 'curso', params: {curso: curso.id}}">
                                {{ curso.nome }} - {{ curso.totalAulas }} aulas | {{ curso.horas }} horas
                            </router-link>
                        </h2>
                        <p>{{ curso.descricao }}</p>
                    </li>
                </ul>
            </div>
        </transition>
    </div>
</template>

<!-- eslint-disable vue/multi-word-component-names -->
<script>
import fetchData from '@/mixins/fetchData';

export default {
    name: "cursos",
    mixins: [fetchData],
    created() {
        this.fetchData('/cursos');
    }
}
</script>

<style>
.cursos-lista li {
    margin-bottom: 40px;
}
</style>