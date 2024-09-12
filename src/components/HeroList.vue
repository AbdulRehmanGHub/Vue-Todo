<template>
    <div class="container">
        <div class="top">
            <h1>HERO LIST APP</h1>
            <ul class="hero-list">
                <li v-for="(hero, index) in heroes" :key="index" class="hero-item">
                    {{ hero }}
                    <span class="remove-button" @click="removeHero(index)">x</span>
                </li>
            </ul>
        </div>
        <div class="add-hero-container">
            <input v-model="newHero" placeholder="Type Hero Name Here" />
            <button @click="addHero">Add Hero</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            heroes: [],
            newHero: ''
        };
    },
    methods: {
        addHero() {
            if (this.newHero.trim() !== '') {
                this.heroes.push(this.newHero.trim());
                this.newHero = '';
            }
        },
        removeHero(index) {
            this.heroes.splice(index, 1);
        }
    }
};
</script>

<style scoped>
body {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-size: 62.5%;
}

.container {
    width: 100%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.hero-list {
    list-style-type: none;
    border: 1px solid #ddd;
    border-radius: 4px;
    width: 98%;
    background-color: white;
    margin-bottom: 2rem;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}

.hero-item {
    display: flex;
    justify-content: space-between;
    padding: 10px;
    border-bottom: 1px solid #ddd;
}

.hero-item:last-child {
    border-bottom: none;
}

.remove-button {
    cursor: pointer;
}

.remove-button:hover {
    color: red;
}

.add-hero-container {
    display: flex;
    justify-content: center;
    align-items: center
}

.add-hero-container input {
    padding: .6rem .4rem;
    border: 1px solid #ddd;
    border-radius: 10px;
    outline: none;
    margin-right: 10px;
}

.add-hero-container button {
    padding: 6px 18px;
    font-size: .8rem;
    border: none;
    background: radial-gradient(circle 916px at 8.2% 2.5%, rgb(223, 41, 80) 0%, rgb(255, 128, 204) 17%, rgba(255, 119, 183, 0.86) 47.2%, rgba(247, 246, 246, 1) 100%);
    ;
    color: white;
    border-radius: 8px;
    cursor: pointer;
    transition: .4s all ease-in-out;
}

.add-hero-container button:hover {
    background: radial-gradient(circle 916px at 8.2% 2.5%, rgb(202, 0, 44) 0%, rgb(138, 60, 107) 17%, rgba(255, 27, 133, 0.86) 47.2%, rgba(247, 246, 246, 1) 100%);
    ;
    transition: .4s all ease-in-out;
}

@media (min-width: 1024px) {
    .container {
        min-width: 700px;
        padding: 4rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .top h1 {
        font-size: 6rem;
    }

    .hero-list {
        border: 2px solid #ddd;
        border-radius: .4rem;
        font-size: 2rem;
        width: 98%;
        background-color: white;
        margin-bottom: 2rem;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
    }

    .hero-item {
        display: flex;
        justify-content: space-between;
        padding: 1rem;
        border-bottom: 1px solid #ddd;
    }

    .add-hero-container input {
        width: 40rem;
        height: 4rem;
        padding: .6rem;
        border: 2px solid #ddd;
        border-radius: .6rem;
        margin-right: 1rem;
        font-size: 2rem;
    }

    .add-hero-container button {
        height: 4rem;
        padding: .8rem 1rem;
        font-size: 2rem;
        border-radius: .8rem;
    }
}
</style>
