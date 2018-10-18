<template>
    <div class="home">
        q 库的使用
    </div>
</template>

<script>
import q from 'q'

export default {
    mounted () {
        this.qConsole()
    },
    methods: {
        qConsole () {
            console.log(q)
        }
    }
}
</script>
