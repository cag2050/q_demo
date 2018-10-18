<template>
    <div class="home">
        q 库的使用
    </div>
</template>

<script>
import Q from 'q'

export default {
    mounted () {
        this.qConsole1()
        this.qConsole2()
    },
    methods: {
        // 使用方法1：
        // Q.Promise((resolve, reject) => {
        qConsole1 () {
            Q.Promise((resolve, reject) => {
                throw new Error('error info')
                resolve('xxx')
            })
                .then((value) => {
                    console.log(value)
                })
                .catch(err => {
                    console.log(err)
                    // throw err
                })
                .finally(() => {
                    console.log('finally')
                    throw new Error('error in finally')
                })
                .done()
        },
        // 使用方法2：
        // Q.resolve().then()
        qConsole2 () {
            Q.resolve()
                .then(() => {
                    return Q.Promise((resolve, reject) => {
                        resolve('2222')
                    })
                })
                .then((value) => {
                    console.log(value)
                })
        }
    }
}
</script>
