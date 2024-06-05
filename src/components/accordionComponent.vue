<script setup>
import { ref } from 'vue'

const items = ref([
    {
        title: "Unlocking Android",
        shortDescription: "Unlocking Android: A Developer's Guide provides concise, hands-on instruction for the Android operating system and development tools. This book teaches important architectural concepts in a straightforward writing style and builds on this with practical and useful examples throughout.",
        longDescription: "Android is an open source mobile phone platform based on the Linux operating system and developed by the Open Handset Alliance, a consortium of over 30 hardware, software and telecom companies that focus on open standards for mobile devices. Led by search giant, Google, Android is designed to deliver a better and more open and cost effective mobile experience.    Unlocking Android: A Developer's Guide provides concise, hands-on instruction for the Android operating system and development tools. This book teaches important architectural concepts in a straightforward writing style and builds on this with practical and useful examples throughout. Based on his mobile development experience and his deep knowledge of the arcane Android technical documentation, the author conveys the know-how you need to develop practical applications that build upon or replace any of Androids features, however small.    Unlocking Android: A Developer's Guide prepares the reader to embrace the platform in easy-to-understand language and builds on this foundation with re-usable Java code examples. It is ideal for corporate and hobbyists alike who have an interest, or a mandate, to deliver software functionality for cell phones.    WHAT'S INSIDE:        * Android's place in the market      * Using the Eclipse environment for Android development      * The Intents - how and why they are used      * Application classes:            o Activity            o Service            o IntentReceiver       * User interface design      * Using the ContentProvider to manage data      * Persisting data with the SQLite database      * Networking examples      * Telephony applications      * Notification methods      * OpenGL, animation & multimedia      * Sample Applications  ",
        open: false,
    },
    {
        title: "Android in Action, Second Edition",
        shortDescription: "Android in Action, Second Edition is a comprehensive tutorial for Android developers. Taking you far beyond \"Hello Android,\" this fast-paced book puts you in the driver's seat as you learn important architectural concepts and implementation strategies. You'll master the SDK, build WebKit apps using HTML 5, and even learn to extend or replace Android's built-in features by building useful and intriguing examples. ",
        longDescription: "When it comes to mobile apps, Android can do almost anything   and with this book, so can you! Android runs on mobile devices ranging from smart phones to tablets to countless special-purpose gadgets. It's the broadest mobile platform available.    Android in Action, Second Edition is a comprehensive tutorial for Android developers. Taking you far beyond \"Hello Android,\" this fast-paced book puts you in the driver's seat as you learn important architectural concepts and implementation strategies. You'll master the SDK, build WebKit apps using HTML 5, and even learn to extend or replace Android's built-in features by building useful and intriguing examples. ",
        open: false,
    }
])

const toggleAccording = (index) => {
    items.value = items.value.map((item, i) => ({
        ...item,
        open: i === index ? !item.open : false
    }))
}
</script>

<template>
    <div class="accordion-container">
        <div v-for="(item, index) in items" :key="index" class="accordion">
            <div class="accordion-header" @click="toggleAccording(index)">
            {{ item.title }}
            <span class="arrow-icon"> {{ item.open ? "▼" : "▶" }} </span>
            <!-- <p class="paragraph"></p> -->
        </div>

        <div v-show="item.open" class="accordion-content">
            {{ item.longDescription }}
        </div>

        </div>
    </div>
</template>

<style scoped>
.accordion-container {
    max-width: 600px;
    margin: 50px auto;
}

.accordion {
    border: 1px solid #ddd;
    border-radius: 4px;
    overflow: hidden;
    margin-bottom: 10px;
}

.accordion-header {
    background-color: #3498db;
    color: #fff;
    padding: 15px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.arrow-icon {
    font-size: 20px;
}

.accordion-content {
    padding: 15px;
    display: none;
    border-top: 1px solid #ddd;
    background-color: #f9f9f9;
    color: #333;
}

.accordion-content[style] {
    display: block;
}

</style>