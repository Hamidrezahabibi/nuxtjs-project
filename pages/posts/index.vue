<template>
    <div class="Posts">
        <div v-for="(post,id) in posts" :key="id">
            <v-card class="mx-auto mb-3" max-width="500">
                <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                height="200px"
                ></v-img>

                <v-card-title>
                    {{ post.title }}
                </v-card-title>

                <v-card-subtitle>
                    {{ post.description }}
                </v-card-subtitle>

                <v-card-actions>
                <v-btn
                    color="orange lighten-2"
                    text
                    :href="'/posts/' + post.id"
                >
                    Open
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn
                    icon
                    @click="show = !show"
                >
                    <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                </v-btn>
                </v-card-actions>

                <v-expand-transition>
                <div v-show="show">
                    <v-divider></v-divider>

                    <v-card-text>
                    I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
                    </v-card-text>
                </div>
                </v-expand-transition>
            </v-card>
        </div>
    </div>
</template>

<script>


export default {
    name: 'Posts',
    async asyncData({$axios}){
        const posts = await $axios.$get("https://api.nuxtjs.dev/posts");
        return { posts };
    }
}
    
        
</script>

