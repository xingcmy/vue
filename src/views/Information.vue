<template>
    <div>
        <table>
            <tr>
                <td>账号</td>
                <td>昵称</td>
                <td>签名</td>
                <td>性别</td>
                <td>生日</td>
                <td>职业</td>
                <td>所在地</td>
            </tr>
            <tr v-for="item in information">
                <td>{{item.id}}</td>
                <td>{{item.name}}</td>
                <td>{{item.signature}}</td>
                <td>{{item.sex}}</td>
                <td>{{item.birthday}}</td>
                <td>{{item.profession}}</td>
                <td>{{item.city}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name: "Information",
        data(){
            return {
                information:[
                    {
                        id: '0',
                        name: '0',
                        signature: '0',
                        sex: '0',
                        birthday: '0',
                        profession: '0',
                        city: '0'
                    }
                ]
            }
        },
        created() {
            const _this = this;
            axios.get('http://localhost:8181/information/findAll').then(function (resp) {
                _this.information=resp.data;
            })
        }


    }
</script>

<style scoped>

</style>