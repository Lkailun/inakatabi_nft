<template>
    <div class="faq">
        <section>
            <header style="font-family: BalooBhainaRegular;">FAQ</header>
            <div v-for="(item, index) in state.faq" :key="index" class="line">
                <div class="top" :class="{ active: state.active === index }">
                    {{ item.ask }}
                    <img v-if="state.active === index" src="../../../assets/images/home/icon-minus.png" alt="" @click="check(index)" />
                    <img v-else src="../../../assets/images/home/icon-Plus.png" alt="" @click="check(index)" />
                </div>
                <div class="cont" :class="{ active: state.active === index }">{{ item.bid }}</div>
            </div>
        </section>
    </div>
</template>
<script setup>
import { reactive } from 'vue';
const state = reactive({
    active: -1,
    faq: [
        { ask: 'What is Kiss Your Dreams?', bid: 'Kiss Your Dreams is an NFT project with a total of 3,333 unique Kiss Your Dreams NFTs We are an ASMR focused project that hopes to enable web3 users to have a completely relaxing sleep environment' },
        { ask: 'Which chain and contract are we using?', bid: 'We are using the Ethereum blockchain, and our main collection will be using the ERC-721 contract' },
        { ask: 'How many mints per wallet?', bid: 'Our whitelist users can cast 2 NFTs for each wallet and enjoy the whitelist price. The remaining unsold inventory (including 888 NFTs in the public coinage plan) in the white list coinage process will be used for public coinage. Each wallet can cast up to 3 NFTs, and the project party reserves 333 as the demand for later activities and lock-in' },
        { ask: 'What are our future plans/roadmap?', bid: 'Please refer to the diary sheet page of our website' },
        { ask: 'When will Kiss Your Dream  be released?', bid: 'Expected in March. A detailed schedule will be announced on Twitter' },
    ],
});

const check = index => {
    state.active = state.active === index ? -1 : index;
};
</script>
<style scoped lang="scss">
.faq {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-content: center;
    background: rgb(124, 155, 215);
    background: url('../../../assets/images/home/faq_bg.jpg') no-repeat, #ff8080;
    /* background-position: 90% bottom; */
    background-size: 100% 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 850px;
    section {
        width: 60%;
        position: relative;
        left: -10%;
        top: 6%;
        header {
            font-size: 64px;
            line-height: 74px;
            margin-bottom: 46px;
            color: #fff;
            font-weight: 700;
        }
        .line {
            width: 100%;
            margin-top: 16px;
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid #f8e3e2;
            background: rgba(255, 255, 255, 0.5);
            .top {
                position: relative;
                width: 100%;
                background: rgba(255, 255, 255, 0.9);
                border-radius: 16px;
                border-bottom-left-radius: 0;
                border-bottom-right-radius: 0;
                transition: border-radius 0.5s;
                padding: 24px 40px;
                display: flex;
                justify-content: space-between;
                align-items: center;

                font-size: 20px;
                font-family: 'Montserrat';
                color: #000;
                font-size: 18px;
                font-weight: 700;
                img {
                    float: right;
                    cursor: pointer;
                    width: 25px;
                }
                &.active {
                    border-radius: 24px;
                }
            }
            .cont {
                font-family: 'Montserrat';
                color: #000;
                font-size: 16px;
                font-weight: 400;
                line-height: 24px;
                height: 0;
                opacity: 0;
                overflow: hidden;
                transform: scaleY(0);
                transition: all 300ms;
                transition: opacity 267ms cubic-bezier(0.4, 0, 0.2, 1) 0ms, transform 178ms cubic-bezier(0.4, 0, 0.2, 1) 0ms;
                transform-origin: 0 0;
                &.active {
                    padding: 24px 40px;
                    height: auto;
                    font-size: 18px;
                    opacity: 1;
                    transform: scaleY(1);
                }
            }
        }
    }
    @media screen and (max-width: 1000px) {
        min-height: 100%;
        section {
            width: 100%;
            padding: 0 16px;
            left: 0;
            top: -7%;
            header {
                font-size: 30px;
                line-height: 34px;
                margin-bottom: 20px;
            }
            .line {
                margin-top: 14px;
                border-radius: 16px;
                .top {
                    padding: 12px 16px;
                    border-radius: 16px;
                    line-height: 24px;
                    &.active {
                        border-radius: 16px;
                    }
                }
                .cont {
                    &.active {
                        padding: 13px 16px;
                        height: auto;
                        font-size: 16px;
                        line-height: 20px;
                    }
                }
            }
        }
    }
}
</style>
