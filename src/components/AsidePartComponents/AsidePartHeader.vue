<template>
    <div class="aside-part-header-wrapper">
        <div class="aside-part-header-inside-wrapper">
            <img src="/public/photo.jpg" width="96px" height="96px" alt="">
            <span class="aside-part-header-person-name">Anurag Yadav</span>
        </div>
        <div class="aside-part-header-person-description">
            <span>A well-organized, creative and goaloriented graduate possessing excellent communication, problem-solving and leadership skills with a flair to explore Computer Science Engineering</span>
        </div>
    </div>
</template>

<script>
</script>

<style scoped>
    img {
        border-radius: 50%;
        object-fit: cover;
        object-position: 50% 0;
    }
    .aside-part-header-wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 32px;
        padding-top: 48px;
    }
    .aside-part-header-inside-wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 16px;
        }
    .aside-part-header-person-description {
        font-family: 'Outfit', sans-serif;
        font-size: 18px;
        font-weight: 500;
        height: 143px;
        width: 298px;
        line-height: 1.33;
        color: rgba(71, 81, 107, 1);
    }
    .aside-part-header-person-name {
        font-family: 'Outfit', sans-serif;
        color: var(--gray-darker, #2E2E48);
        font-size: 32px;
        font-style: normal;
        font-weight: 500;
        line-height: 1.25;
    }
    @media screen and (max-width: 1190px)  {
        .aside-part-header-inside-wrapper {
            display: flex;
            flex-direction: row;
            column-gap: 15px;
            padding-bottom: 4%;
        }
        .aside-part-header-person-name {
            font-size: 24px;
            padding-top: 24px;
        }
        .aside-part-header-wrapper {
            row-gap: 3vh;
        }
    }
    @media screen and (min-width: 650px) and (max-width: 800px) {
        .aside-part-header-wrapper {
            display: flex;
            flex-direction: row;
            row-gap: 10px;
            padding-top: 48px;
        }
        .aside-part-header-inside-wrapper {
            padding-bottom: 0px;
        }
        .aside-part-header-person-description {
            padding-left: 15px;
            font-size: 14px;
            min-width: 238px;
            height: auto;
        }
    }
    @media screen and (min-width: 400px) and (max-width: 650px) {
        .aside-part-header-person-description {
            margin-left: auto;
            margin-right: auto;
        }
        .aside-part-header-inside-wrapper{
            margin-left: auto;
            margin-right: auto;
        }
    }
</style>