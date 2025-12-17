<template>
    <section class="about">
        <div class="my-container about-item">
            <div class="about-item-img">
                <!-- <img src="/images/about.png" alt=""> -->
                <img src="/images/about-1.png" alt="">
            </div>
            <div class="about-item-text">
                <h3>ABOUT</h3>
                <p>I’m Majid.
                    Went from the kitchen to programming.
                    Started from zero: wrote terrible code, struggled with every bug, did a lot by trial and error.
                    Now I work on frontend — React, Next.js, Vue, TypeScript.
                    <br><br>
                    A bit of Python/Django too, just to understand what’s happening on the backend.
                    I don’t aim for perfection — I aim for results that actually work.
                    Everything I do, I see through to the end, learning from mistakes and moving forward.
                </p>
            </div>
        </div>
    </section>
</template>

<style>
.about {
    background: linear-gradient(180deg, #000 0%, rgba(37, 37, 37, 0) 290%);
    padding: 70px 0;

    .about-item {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 150px;

        .about-item-img {
            width: 303px;
            border-radius: 100%;
            min-width: 303px;
        }

        .about-item-text {
            h3 {
                font-family: var(--font-family);
                font-weight: 600;
                font-size: 40px;
                letter-spacing: 0.15em;
                color: #fff;
                padding-bottom: 24px;
            }

            p {
                font-family: var(--font-family);
                font-weight: 400;
                font-size: 16px;
                line-height: 153%;
                letter-spacing: 0.03em;
                color: #fff;
            }
        }
    }
}

@media (max-width: 1000px) {
    .about-item{
        gap:  40px !important ;
    }
}

@media (max-width: 769px) {
    .about {
        padding: 50px 0;

        .about-item {
            flex-direction: column;
            text-align: center;
            gap: 40px;

            .about-item-img {
                width: 200px;
                min-width: 200px;
            }

            .about-item-text {
                h3 {
                    font-size: 32px;
                }
            }

            .about-item-img {
                width: 70%;
                min-width: unset;
                margin: 0 auto;

                img {
                    width: 100%;
                }
            }
        }
    }
}
</style>