<template>
    <div class="container">
        <div class="row mt-5">
            <template v-if="projects.length > 0">
                <div class="col-4" v-for="project in projects" :key="project.id">
                    <CardProjectComponent :project="project" />
                </div>
            </template>
            <template v-else>
                <Suspense>
                    <template #default>
                        <div class="col-4" v-for="n in 3" :key="n">
                            <SkeletonCardProjectComponent />
                        </div>
                    </template>
                    <template #fallback>
                        <div>Error: Failed to fetch projects.</div>
                    </template>
                </Suspense>
            </template>
        </div>
    </div>
</template>

<script>
import { ref, onMounted, Suspense } from 'vue';
import axios from 'axios';
import CardProjectComponent from '../components/CardProject/CardProjectComponent.vue';
import SkeletonCardProjectComponent from '../components/CardProject/SkeletonCardProjectComponent.vue';

export default {
    components: {
        CardProjectComponent,
        SkeletonCardProjectComponent,
        Suspense,
    },

    setup() {
        const projects = ref([]);

        const getProjects = () => {
            axios
                .get('http://localhost:3000/api/v1/project')
                .then(response => {
                    projects.value = response.data.data;
                })
                .catch(error => {
                    console.log(error);
                });
        };

        onMounted(getProjects);

        return {
            projects,
        };
    },
};
</script>

<style></style>
