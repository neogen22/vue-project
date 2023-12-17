<template>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;500&display=swap" rel="stylesheet">
    <div class="wrapper">
        <div class="wrapper-inside">
            <img src="../icons/photo.jpg" width="96px" height="96px" alt="">
            <div class="person-name">Anurag Yadav</div>
        </div>
        <div class="person-description">
            <div>A well-organized, creative and goaloriented graduate possessing excellent communication, problem-solving and leadership skills with a flair to explore Computer Science Engineering</div>
        </div>
    </div>    
</template>

<script>
</script>

<style scoped>
    img {
        border-radius: 50%;
    }
    .person-description {
        font-family: 'Outfit', sans-serif;
        font-size: 18px;
        font-weight: medium;
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