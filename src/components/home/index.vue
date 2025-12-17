<template>
    <section class="home">
        <div class="home-item my-container flex items-center justify-between">
            <div class="home-item-text">
                <h2 class="">
                    Hello, It’s Me
                </h2>
                <h1 class="">Abdumazhid</h1>
                <h4>Bringing ideas to life through <br> pixels and code </h4>
                <button>Resume</button>
            </div>
            <div class="home-item-img max-w-[503px]">
                <img src="/images/home.png" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped>
.home {
    background: #000;
    padding-top: 30px;
    padding-bottom: 30px;

    .home-item {
        .home-item-text {
            h2 {
                font-family: var(--font-family);
                font-weight: 700;
                font-size: 32px;
                color: #fff;
            }

            h1 {
                font-family: var(--font-family);
                font-weight: 700;
                font-size: 48px;
                letter-spacing: 0.05em;
                text-align: justify;
                color: #fff;
                padding: 23px 0 29px;
            }

            h4 {
                font-family: var(--font-family);
                font-weight: 400;
                font-size: 24px;
                line-height: 160%;
                color: #fff;
            }

            button {
                margin-top: 20px;
                border: 3px solid #fff;
                border-radius: 40px;
                background: #ffffff;
                font-family: var(--font-family);
                font-weight: 600;
                font-size: 20px;
                line-height: 200%;
                letter-spacing: 0.17em;
                text-align: center;
                color: #000;
                padding: 8px 64px;

            }
        }


    }
}

@media (max-width: 768px) {
    .home {
        padding-top: 0;
        padding-bottom: 60px;
        .home-item {
            flex-direction: column-reverse;
            gap: 30px;

            .home-item-text {
                text-align: center;

                h1 {
                    font-size: 36px;
                    text-align: center;

                }
            }
        }
    }
}
</style>
