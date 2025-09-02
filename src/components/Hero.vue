<script setup>
// Tug'ilgan yil
const birthYear = 2009

// Yoshni avtomatik hisoblash
const currentYear = new Date().getFullYear()
const age = currentYear - birthYear

function scrollToContact() {
    const element = document.querySelector("#contact")
    if (element) {
        element.scrollIntoView({ behavior: "smooth" })
    }
}
</script>

<template>
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-grid">
                <!-- Text Content -->
                <div class="text-content">
                    <div class="badge">Frontend Dasturchi</div>

                    <h1 class="title">
                        Salom, Men <span class="highlight">Behruz</span>
                    </h1>

                    <p class="subtitle">
                        Men hozirda {{ age }} yoshdaman. Veb-sayt va ilovalar yaratish
                        bo‘yicha faol ishlayman. Men haqimdagi batafsil ma’lumotni
                        alohida sahifadan ko‘rishingiz mumkin.
                    </p>

                    <div class="buttons">
                        <button class="btn primary" @click="scrollToContact">
                            <img class="icon" src="/icons/message.png" alt=""> Bog'lanish
                        </button>
                        <a href="/Behruz_Qahramonov_CV.pdf" download><button class="btn outline">
                                <img class="icon" src="/icons/download.png" alt=""> CV Yuklab olish
                            </button></a>
                    </div>

                    <div class="socials">
                        <a href="https://github.com/WebBola" target="_blank" class="btn"><img class="icon"
                                src="/icons/github.png" alt=""></a>
                        <a href="https://t.me/behruz8005" target="_blank" class="btn"><img class="icon"
                                src="/icons/telegram.png" alt=""></a>
                        <a href="https://www.instagram.com/dyrroth.n1/" target="_blank" class="btn"><img class="icon"
                                src="/icons/instagram.png" alt=""></a>
                    </div>
                </div>

                <!-- Profile Image -->
                <div class="image-wrapper">
                    <div class="profile-pic">
                        <img src="/images/my.png" alt="Behruz - Frontend Dasturchi" />
                    </div>
                    <div class="experience">
                        <p>2+ yil tajriba</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap");

.hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 0px 20px 40px;
}

.hero-grid {
    width: 100%;
    display: flex;
    gap: 40px;
    align-items: center;
    justify-content: space-between;
}

@media (min-width: 1024px) {
    .hero-grid {
        grid-template-columns: 1fr 1fr;
    }
}


.text-content {
    max-width: 700px;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 60px;
}

.badge {
    width: fit-content;
    display: inline-block;
    background: #f3f4f6;
    color: #374151;
    padding: 6px 12px;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    margin-top: 40px;
}

.title {
    font-size: 56px;
    line-height: 1.2;
    font-weight: normal;
}

@media (max-width: 1024px) {
    .title {
        font-size: 36px;
    }
}

.subtitle {
    font-size: 16px;
    color: #6b7280;
}

.buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}

.btn {
    padding: 6px 20px;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    transition: 0.2s;
    cursor: pointer;
    font-family: 'Inter' sans-serif;
    font-weight: 600;
}


.btn.primary {
    background: #000;
    font-size: 12px;
    color: white;
    border: none;
}

.btn.primary .icon {
    margin-bottom: -3px;
}

.btn.outline {
    font-size: 12px;
    background: none;
    color: black;
    font-weight: 500;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid rgba(128, 128, 128, 0.338);
    cursor: pointer;
}

.btn.icon {
    border: 2px solid #d1d5db;
    background: none;
    padding: 10px 14px;
    font-size: 14px;
    border-radius: 8px;
}

.buttons .btn .icon {
    margin-right: 5px;
}

.socials {
    display: flex;
    gap: 12px;
}

.socials .btn {
    width: 20px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid rgba(128, 128, 128, 0.338);
    cursor: pointer;
}

.image-wrapper {
    width: 320px;
    height: 320px;
    display: flex;
    justify-content: center;
    position: relative;
    margin-bottom: -50px;
}

.profile-pic {
    width: 320px;
    height: 320px;
    border-radius: 50%;
    overflow: hidden;
    border: 4px solid #0000006c;
}

.profile-pic img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.experience {
    position: absolute;
    bottom: -10px;
    right: 10px;
    background: #000000;
    border: 2px solid white;
    color: white;
    padding: 8px 14px;
    border-radius: 10px;
    font-size: 14px;
}

.icon {
    height: 15px;
}

@media (max-width: 767px) {
    .hero-grid {
        flex-wrap: wrap;
    }

    .image-wrapper {
        margin: 0 auto;
        width: 280px;
        height: 280px;
    }


    .profile-pic {
        width: 280px;
        height: 280px;
        border-radius: 50%;
        overflow: hidden;
        border: 4px solid #0000006c;
    }
}
</style>
