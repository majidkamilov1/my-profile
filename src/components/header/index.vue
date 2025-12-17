<template>
    <header class="header bg-[#000]">
        <div class="header-items my-container !py-[32px] flex justify-between items-center">
            <h4 class="">Majid</h4>
            <ul class="flex gap-[30px] max-[900px]:gap-[15px]">
                <li><a class="" href="About">About</a></li>
                <li><a class="" href="Skills">Skills</a></li>
                <li><a class="" href="Projects">Projects</a></li>
                <li><a class="" href="Contact">Contact</a></li>
                <li><a class="" href="Contact">kamilov1majid@gmail.com</a></li>
            </ul>
            <button class="header-item-menu">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </header>
</template>

<style scoped>
.header-items {
    >h4 {
        font-family: var(--font4);
        font-weight: 400;
        font-size: 36px;
        line-height: 83%;
        letter-spacing: 0.2em;
        text-align: center;
        color: #fff;
    }

    ul li a {
        font-family: var(--font-family);
        font-weight: 500;
        font-size: 16px;
        color: #fff;
    }

    .header-item-menu {
        display: none;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        span {
            display: block;
            width: 25px;
            height: 3px;
            margin-bottom: 5px;
            background-color: #fff;
            border-radius: 2px;
        }
    }

    @media (max-width: 768px) {
        .header-item-menu {
            display: flex;
        }

        ul {
            display: none;
        }
    }
}
</style>