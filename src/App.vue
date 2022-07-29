<template>
    <div id="App">
        <!-- Вешаем обработчик на кнопку для открытия модального окна -->
        <button class="button" @click = "showModal">Открыть окно</button>
        <!-- Используем ref, чтобы затем обратиться к модальному окну -->
        <ModalWindow ref="modal"></ModalWindow>
    </div>
</template>

<script>

import ModalWindow from './components/ModalWindow.vue';

export default {
    components: {
        'ModalWindow': ModalWindow,
    },

    data() {
        return {
        }
    },

    methods: {
        showModal () {
            this.$refs.modal.isModalVisible = true; //Показываем модальное окно при нажатии на кнопку
        },
    }
}
</script>


<style>

    body {
        font-family: 'Source Sans Pro', sans-serif;
        margin: 0;
        padding: 0;
        height: 100%;
    }
 
    #App {
        position: relative;
        width: 100%;
        min-height: 100%;
    }

    .button {
        background-color: #0971c7;
        color: #fff;
        border: none;
        text-align: center;
        padding: 8px;
        font-size: 17px;
        font-weight: 500;
        border-radius: 8px;
        min-width: 150px;
    }

</style>
