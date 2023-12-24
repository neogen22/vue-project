<template>    
    <div class="wrapper">
        <div class="wrapper-inside">
            <img src="/public/photo.jpg" width="96px" height="96px" alt="">
            <span class="person-name">Anurag Yadav</span>
        </div>
        <div class="person-description">
            <span>A well-organized, creative and goaloriented graduate possessing excellent communication, problem-solving and leadership skills with a flair to explore Computer Science Engineering</span>
        </div>
    </div>    
</template>

<script>
</script>

<style scoped>
    @media (orientation: portrait) {        
        .wrapper-inside {
            display: flex;
            flex-direction: row;
            column-gap: 10%;
            padding-bottom: 4%;
        }
        .person-description {
            font-family: 'Outfit', sans-serif;
            font-size: 3vw;
            font-weight: 500;            
            line-height: 1.33;
            color: rgba(71, 81, 107, 1);
            text-align: center;
        }
        .person-name {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 7vw;
            font-style: normal;
            font-weight: 500;
            line-height: 1.25;
            padding-top: 7%;
        }
    }
    img {
        border-radius: 50%;
        object-fit: cover;
        object-position: 50% 0;
    }
    @media (orientation: landscape) {
        .wrapper {
            display: flex;
            flex-direction: column;
            row-gap: 32px;
            padding-top: 48px;
        }
        .wrapper-inside {
            display: flex;
            flex-direction: column;
            row-gap: 16px;
        }
        .person-description {
            font-family: 'Outfit', sans-serif;
            font-size: 18px;
            font-weight: 500;
            height: 143px; 
            width: 298px;
            line-height: 1.33;
            color: rgba(71, 81, 107, 1);
        }
        .person-name {
            font-family: 'Outfit', sans-serif;
            color: var(--gray-darker, #2E2E48);
            font-size: 32px;
            font-style: normal;
            font-weight: 500;
            line-height: 1.25;
        }
    }
</style>