<template>
    <div class="gamesBox">
        <ul id="sportsLi">
            <li v-for="({ icon, title, id }) in sports" :key="id">
                <img :src="icon" alt="">
                <p>{{ title }}</p>
            </li>
        </ul>

        <div id="gamesListFooter">
            <img src="/icons-banner-hero/tournamentIcon.svg" alt="Torneios da comunidade">
        </div>
    </div>
</template>

<script>
export default {
    name: "esportsList",
    data: () => ({
        sports: [
            { icon: 'icons-banner-hero/sport-1.png', title: 'Hearthstone® masters', id: 0 },
            { icon: 'icons-banner-hero/sport-2.png', title: 'Campeonato Mundial de Arena WoW®', id: 0 },
            { icon: 'icons-banner-hero/sport-3.png', title: 'StarCraft® II WCS', id: 0 },
            { icon: 'icons-banner-hero/sport-4.png', title: 'Copa Mundial de Overwatch®', id: 0 },
        ]
    }),
}
</script>



<style src="../../../assets/scss/header/gamesList.scss" scoped/>


