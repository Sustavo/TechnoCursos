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
                <ul>
                    <li>
                        <b>Email: </b>
                        {{ api.contato.email }}
                    </li>
                    <li>
                        <b>Telefone: </b>
                        {{ api.contato.telefone }}
                    </li>
                    <li>
                        <b>Endereco: </b>
                        {{ api.contato.endereco }}
                    </li>
                </ul>
            </div>
        </transition>
    </div>
</template>

<!-- eslint-disable vue/multi-word-component-names -->
<script>
import fetchData from '@/mixins/fetchData'

export default {
    name: "contato",
    mixins: [fetchData],
    created() {
        this.fetchData('/contato');
    }
}
</script>

<style>

</style>