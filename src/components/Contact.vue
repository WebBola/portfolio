<script setup>
import { reactive } from "vue"

const formData = reactive({
    name: "",
    phone: "",
    message: ""
})

const handleSubmit = () => {

    let bot_token = '8242549919:AAF-N7u2WR8XwFPT5_WvyIKAuOuhCZhGMB4';
    let user_id = '7760337711';

    let msg = `
✨ Yangi xabar keldi!
-------------------------
👤 Ism: ${formData.name}
📞 Telefon: ${formData.phone}
💬 Xabar:
${formData.message}
-------------------------
`

    fetch(`https://api.telegram.org/bot${bot_token}/sendMessage?chat_id=${user_id}&text=${encodeURIComponent(msg)}`)
        .then(res => {
            if (res.ok) {
                alert("✅ Xabaringiz yuborildi! Tez orada javob beraman.")
                console.log("Form yuborildi:", formData)

                formData.name = ""
                formData.phone = ""
                formData.message = ""
            } else {
                alert("❌ Xabar yuborilmadi. Qaytadan urinib ko‘ring.")
            }
        })
        .catch(err => {
            console.error("Xato:", err)
            alert("❌ Internetda yoki botda muammo bor.")
        })
}


const contactInfo = [
    {
        icon: "/icons/email.png",
        title: "Email",
        value: "webdasturchi2009@gmail.com",
        link: "mailto:webdasturchi2009@gmail.com"
    },
    {
        icon: "/icons/telephone.png",
        title: "Telefon",
        value: "+998 94 021 33 03",
        link: "tel:+998940213303"
    },
    {
        icon: "/icons/location.png",
        title: "Joylashgan o'rni",
        value: "Toshkent, O'zbekiston",
        link: ""
    }
]

const socialLinks = [
    {
        icon: "/icons/github.png",
        name: "GitHub",
        url: "https://github.com/WebBola",
        username: "@WebBola"
    },
    {
        icon: "/icons/telegram.png",
        name: "Telegram",
        url: "https://t.me/behruz8005",
        username: "@behruz8005"
    },
    {
        icon: "/icons/instagram.png",
        name: "Instagram",
        url: "https://www.instagram.com/dyrroth.n1/",
        username: "@dyrroth.n1"
    }
]
</script>

<template>
    <section id="contact" class="contact">
        <div class="container">
            <div class="text-center">
                <div class="badge">Bog‘lanish</div>
                <h2 class="title">Keling, Birga Ishlaylik</h2>
                <p class="subtitle">
                    Sizning loyihangiz bo‘yicha gaplashishdan xursand bo‘laman.
                    Menga xabar yozing yoki to‘g‘ridan-to‘g‘ri qo‘ng‘iroq qiling.
                </p>
            </div>

            <div class="grid">
                <!-- Contact Form -->
                <div class="card">
                    <h3 class="card-title">Xabar Yuborish</h3>
                    <form @submit.prevent="handleSubmit" class="form">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="name">Ismingiz *</label>
                                <input v-model="formData.name" id="name" name="name" required
                                    placeholder="Ismingizni kiriting" />
                            </div>
                            <div class="form-group">
                                <label for="email">Phone *</label>
                                <input v-model="formData.phone" id="email" type="number" name="email" required
                                    placeholder="Telefon raqamingizni kiriting" />
                            </div>
                        </div>


                        <div class="form-group">
                            <label for="message">Xabar *</label>
                            <textarea v-model="formData.message" id="message" rows="5" required
                                placeholder="Sizning xabaringiz..."></textarea>
                        </div>

                        <button type="submit" class="btn w-full"><img src="/icons/send.png" alt=""
                                class="icon icon_send"> Xabar Yuborish</button>
                    </form>
                </div>

                <!-- Contact Info -->
                <div class="info-col">
                    <div class="card">
                        <h3 class="card-title">Bog‘lanish Ma'lumotlari</h3>
                        <div class="space">
                            <div v-for="(info, i) in contactInfo" :key="i" class="info-item">
                                <div class="icon_box">
                                    <img :src="info.icon" alt="" class="icon">
                                </div>
                                <div>
                                    <p class="label">{{ info.title }}</p>
                                    <a class="smllTxt" v-if="info.link" :href="info.link">{{ info.value }}</a>
                                    <p v-else>{{ info.value }}</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="card">
                        <h3 class="card-title">Ijtimoiy Tarmoqlar</h3>
                        <div class="space">
                            <div v-for="(social, i) in socialLinks" :key="i" class="info-item info-itembtns">
                                <div class="social_left">
                                    <div class="icon_box">
                                        <img :src="social.icon" alt="" class="icon">
                                    </div>
                                    <div class="flex-1">
                                        <p>{{ social.name }}</p>
                                        <p class="label">{{ social.username }}</p>
                                    </div>
                                </div>
                                <a :href="social.url" target="_blank" class="btn small">Kirish</a>
                            </div>
                        </div>
                    </div>

                    <div class="highlight">
                        <h3>Loyiha Muhokamasi</h3>
                        <p>
                            Loyihangiz haqida batafsilroq gaplashish uchun video qo‘ng‘iroq qilaylikmi?
                        </p>
                        <a :href="contactInfo[1].link" class="btn"><img src="/icons/white_phone.png" alt=""
                                class="btnIcon"> Qo‘ng‘iroq
                            Rejalashtirish</a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.contact {
    padding: 80px 20px;
}

.container {
    max-width: 1300px;
    margin: 0 auto;
}

.text-center {
    text-align: center;
    margin-bottom: 40px;
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
    margin-bottom: 10px;
}

.title {
    font-size: 32px;
    font-weight: 400;
    margin-bottom: 16px;
}


.subtitle {
    color: #6b7280;
    font-size: 17px;
    max-width: 700px;
    margin: auto;
}

.grid {
    display: grid;
    gap: 20px;
}

@media(min-width: 992px) {
    .grid {
        grid-template-columns: 1fr 1fr;
    }
}

.card {
    border: 1px solid #e5e7eb;
    padding: 20px;
    margin: 10px 0;
    border-radius: 12px;
    background: #fff;
}

.card-title {
    font-size: 16px;
    font-weight: 400;
    margin-bottom: 16px;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.form .btn {
    padding-top: 7px;
    padding-bottom: 7px;
    font-size: 13px;
    font-weight: 500;
}

.form-row {
    display: grid;
    gap: 16px;
}

@media(min-width: 768px) {
    .form-row {
        grid-template-columns: 1fr 1fr;
    }
}

.form-group label {
    display: block;
    margin-bottom: 6px;
    font-size: 14px;
}

.form-group input,
.form-group textarea {
    width: 100%;
    background: rgba(128, 128, 128, 0.107);
    border: 1px solid #d1d5db;
    border-radius: 6px;
    padding: 5px 10px;
    font-size: 13px;
}

.btn {
    background: #0a0a1f;
    color: #fff;
    padding: 12px 18px;
    border: none;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    transition: all 0.3s ease;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
}

.btn:hover {
    background: #111133;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.btn.small {
    padding: 8px 14px;
    font-size: 13px;
}

.w-full {
    width: 100%;
}

.info-item {
    display: flex;
    align-items: center;
    gap: 12px;
}

.info-itembtns {
    justify-content: space-between;
}

.smllTxt {
    color: #000;
    font-weight: normal;
    font-size: 15px;
}

.btnIcon {
    height: 20px;
}

.icon_box {
    width: 40px;
    height: 40px;
    background: #f3f4f6;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 18px;
}

.icon {
    height: 18px;
}

.label {
    font-size: 14px;
    color: #6b7280;
}

.space {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.highlight {
    text-align: center;
    padding: 20px;
    background: #f3f4f6;
    border-radius: 12px;
}

.highlight h3 {
    margin-bottom: 10px;
    font-size: 15px;
}

.highlight p {
    margin-bottom: 12px;
    color: #6b7280;
    font-size: 14px;
}

.highlight .btn {
    padding: 7px 20px;
    font-size: 13px;
    font-weight: normal;
}

.highlight a img {
    height: 15px;
}

.social_left {
    display: flex;
    gap: 10px;
}


.icon_send {
    height: 15px;
}

#message {
    resize: vertical;
}
</style>
