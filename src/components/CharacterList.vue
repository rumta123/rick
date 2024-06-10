<template>

        <div className ='filter'>
            <input v-model="filters.name" placeholder="Name" />
            <select v-model="filters.status">
                <option value="">Any Status</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>
            <button @click="applyFilters">Apply</button>
        </div>

        <section class="character-list">
            <CharacterCard v-for="character in characters" :key="character.id" :character="character" />
        </section>

        <div class="pagination">
            <button @click="changePage(page - 1)" :disabled="page === 1">Previous</button>
            <button @click="changePage(page + 1)" :disabled="page === totalPages">Next</button>
        </div>

</template>

<script>
import axios from 'axios';
import CharacterCard from './CharacterCard.vue';

export default {
    name: 'CharacterList',
    components: { CharacterCard },
    data() {
        return {
            characters: [],
            page: 1,
            totalPages: 1,
            filters: {
                name: '',
                status: ''
            }
        };
    },
    methods: {
        fetchCharacters() {
            const params = {
                page: this.page,
                name: this.filters.name,
                status: this.filters.status
            };

            axios.get('https://rickandmortyapi.com/api/character', { params })
                .then(response => {
                    this.characters = response.data.results;
                    this.totalPages = response.data.info.pages;
                })
                .catch(error => {
                    console.error('Error fetching characters:', error);
                });
        },
        changePage(newPage) {
            if (newPage > 0 && newPage <= this.totalPages) {
                this.page = newPage;
                this.fetchCharacters();
            }
        },
        applyFilters() {
            this.page = 1;
            this.fetchCharacters();
        }
    },
    created() {
        this.fetchCharacters();
    }
}
</script>

<style>
.filter{
    display: flex;
    
}
.character-list {
    display: flex;
    -webkit-box-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    align-items: center;
    flex-wrap: wrap;
    max-width: 1920px;
}
.filter{
    justify-content: center;
}

</style>