<template>
    <div class="recommends">
        <div v-for="item in recommends" class="recommend-item">
            <a :href="item.link">
                <img :src="item.image" />
                <div>{{item.title}}</div>
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Recommends",

        props: {
            recommends: {
                type: Array,
                default() {
                    return [];
                }
            }
        }
    }
</script>

<style scoped>

    .recommends {
        display: flex;
        text-align: center;
        font-size: 12px;
        padding: 10px 0px 20px;
        border-bottom: 10px solid #eee;
    }

    .recommend-item {
        flex: 1;
    }
    .recommends img {
        width: 70px;
        height: 70px;
        margin-bottom: 10px;
    }

</style>