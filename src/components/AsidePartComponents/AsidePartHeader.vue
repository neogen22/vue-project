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
/*     @media (orientation: portrait) {
        .aside-part-header-inside-wrapper {
            display: flex;
            flex-direction: row;
            column-gap: 10%;
            padding-bottom: 4%;
        }
        .aside-part-header-person-description {
            font-family: 'Outfit', sans-serif;
            font-size: 3vw;
            font-weight: 500;            
            line-height: 1.33;
            color: rgba(71, 81, 107, 1);
            text-align: center;
        }
        .aside-part-header-person-name {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 7vw;
            font-style: normal;
            font-weight: 500;
            line-height: 1.25;
            padding-top: 7%;
        }
       
    } */
  
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
</style>