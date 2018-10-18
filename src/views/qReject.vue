<template>
    <div class="home">
        Q.reject
    </div>
</template>

<script>
import Q from 'q'

export default {
    mounted () {
        this.qConsole()
    },
    methods: {
        qConsole () {
            Q.reject(new Error('reject的error'))
                .done()
        }
    }
}
</script>
