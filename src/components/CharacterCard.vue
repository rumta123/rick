<template>
  
        <article class="characterCard__Wrapper-sc-1ejywvi-0 bEklxv">
            <div class="characterCard__ImgWrapper-sc-1ejywvi-1 fkUcVI">
                <img :src="character.image" :alt="character.name">
            </div>
            <div class="characterCard__ContentWrapper-sc-1ejywvi-2 isMAic">
                <div class="section">
                    <h2>{{ character.name }}</h2>
                    <span class="status">
                        <span class="status__icon"></span> {{ character.status }} - {{ character.species }}
                    </span>
                </div>
                <div class="section">
                    <span class="text-gray">Last known location:</span>
                    <span>{{ character.location.name }}</span>
                </div>
                <div class="section">
                    <span class="text-gray">First seen in:</span>
                    <span>{{ character.episode[0].name }}</span>
                </div>
            </div>
        </article>


</template>

<script>
export default {
    name: 'CharacterCard',
    props: {
        character: Object
    }
}
</script>



<style scoped>
.CtDrW {
    display: flex;
    -webkit-box-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    align-items: center;
    padding: 4.5rem 0px;
    background: rgb(39, 43, 51);
    min-height: calc(-60px + 50vh);
}
.hVhElu {
    display: flex;
    -webkit-box-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    align-items: center;
    flex-wrap: wrap;
    max-width: 1920px;
}
.bEklxv {
    width: 600px;
    height: 220px;
    display: flex;
    overflow: hidden;
    background: rgb(60, 62, 68);
    border-radius: 0.5rem;
    margin: 0.75rem;
    box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 6px -1px, rgba(0, 0, 0, 0.06) 0px 2px 4px -1px;
}
.fkUcVI {
    flex: 2 1 0%;
    width: 100%;
}
.fkUcVI img {
    width: 100%;
    height: 100%;
    margin: 0px;
    opacity: 1;
    transition: opacity 0.5s ease 0s;
    object-position: center center;
    object-fit: cover;
}


img {
    width: 100%;
    height: auto;
    display: block;
}
img {
    max-width: 100%;
    margin-left: 0;
    margin-right: 0;
    margin-top: 0;
    padding-bottom: 0;
    padding-left: 0;
    padding-right: 0;
    padding-top: 0;
    margin-bottom: 0.8125rem;
}
img {
    border-style: none;
}
.isMAic {
    flex: 3 1 0%;
    position: relative;
    padding: 0.75rem;
    color: rgb(255, 255, 255);
    display: flex;
    flex-direction: column;
}
.isMAic .section:first-child {
    -webkit-box-pack: start;
    justify-content: flex-start;
}

.isMAic .section {
    flex: 1 1 0%;
    display: flex;
    flex-direction: column;
    -webkit-box-pack: center;
    justify-content: center;
}
.isMAic a {
    color: rgb(245, 245, 245);
}
.isMAic .status {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    text-transform: capitalize;
}

.isMAic span {
    font-size: 16px;
    font-weight: 500;
}


.isMAic span, .isMAic h2 {
    margin: 0px;
    padding: 0px;
}
</style>