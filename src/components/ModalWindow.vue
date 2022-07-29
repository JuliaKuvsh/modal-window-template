<template>
    <!-- Используем директиву v-show, чтобы скрывать и показывать модальное окно -->
    <div v-show="isModalVisible" class="modal-window" id="draggable" autofocus>
        <div class="modal-window__header">
            <h2 class="modal-window__title">
                <!-- Создаем слоты под добавление произвольного контента -->
                <slot>{{header}}</slot>
            </h2>
            <!-- Добавляем обработчик клика на кнопку -->
            <button class="modal-window__close" @click ="closeModal" >&#10006;</button>
        </div>
        <div class="modal-window__content">
            <!-- Создаем слоты под добавление произвольного контента -->
            <slot>{{content}}</slot>
        </div>
    </div>
</template>

<script>
export default {
    name: "ModalWindow",
    data() {
        return {
            isModalVisible: false, //Задаем модальному окну скрытое значение по умолчанию
            header: 'Заголовок',
            content: 'Текст модального окна'
        }
    },
    methods: {
     closeModal () {
       this.isModalVisible = false; //Скрываем модальное окно при нажатии на кнопку
     }

    }
}
</script>


<style>
* {
    margin: 0;
    padding: 0;
}

.modal-window {
    border: 2px solid #c5d0e6;
    background: #fff;
    border-radius: 8px;
    padding: 15px;
    min-width: 420px;
    max-width: 480px;
    position: absolute;
    top: 50%;
    left: 35%;
}

.modal-window__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.modal-window__close {
    border-radius: 50%;
    color: #fff;
    background: #2a4cc7;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 7px;
    right: 7px;
    width: 30px;
    height: 30px;
    cursor: pointer;
}

.modal-window__title {
    color: #0971c7;
}

.modal-window__content {
    margin-top: 20px;
}

</style>
