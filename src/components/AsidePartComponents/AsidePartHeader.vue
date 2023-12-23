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
    img {
        border-radius: 50%;
        object-fit: cover;
        object-position: 50% 0%;
    }
    .person-description {
        font-family: 'Outfit', sans-serif;
        font-size: 18px;
        font-weight: 500;
        height:143px; 
        width: 298px;
        line-height: 24px;
        color: rgba(71, 81, 107, 1);
    }    
    .person-name {
        font-family: 'Outfit', sans-serif;
        color: var(--Gray-Dark, #47516B);
        color: var(--Gray-Darker, #2E2E48);
        font-size: 32.269px;
        font-style: normal;
        font-weight: 500;
        line-height: 40.337px;
        letter-spacing: -0.645px; 
    }    
    .wrapper {
        display: flex;
        flex-direction: column;
        row-gap: 32.27px;
        padding-top: 48px;
    }
    .wrapper-inside {
        display: flex;
        flex-direction: column;
        row-gap: 16.13px;
    }
</style>