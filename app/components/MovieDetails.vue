<template>
    <GridLayout columns="3*, 7*" rows="*, *" width="100%">
        <Image @onTap="onTap" :src="imageUrl" row="0" col="0" rowSpan="4"  class="thumbnail"/>
        <Label @onTap="onTap" :text="movie.title" row="0" col="1" class="list-group-item-heading label-text"
               style="width: 60%"/>
        <Label @onTap="onTap" :text="movie.length" row="1" col="1" class="list-group-item-heading label-text"
               style="width: 60%"/>
    </GridLayout>
</template>

<script>
    import MovieRentals from '@/components/MovieRentals';

    export default {
        data() {
            return {}
        },
        computed: {
            imageUrl: function () {
                return "https://codeflare.tech/images/movie_" + this.movie.id + ".jpg";
            },
        },
        methods: {
            onTap: function () {
                // console.log("Item with name: " + this.customer.name + " tapped");
                this.$navigateTo(MovieRentals, {
                    props: {
                        id: this.movie.id
                    }
                });

            }
        },
        props: ['movie'],
        components: {
            MovieRentals
        },
        mounted() {
        }
    }
</script>

<style scoped>
    .label-text {
        font-size: 14;
        color: #444444;
    }
</style>
