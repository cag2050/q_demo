<template>
    <div class="home">
        q 库的使用
    </div>
</template>

<script>
import q from 'q'

export default {
    mounted () {
        // this.qConsole1()
        this.qConsole2()
    },
    methods: {
        // 使用方法1：
        // q.Promise((resolve, reject) => {
        qConsole1 () {
            q.Promise((resolve, reject) => {
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
        // q.resolve().then()
        qConsole2 () {
            q.resolve()
                .then(() => {
                    return q.Promise((resolve, reject) => {
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
