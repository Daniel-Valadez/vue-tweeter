<script>
export default {
    methods: {
        closeModal() {
            this.$emit("close");
            //console.log('Close Modal function')
        },
        errorMessage() {
            alert("Please fill both areas before proceeding...");
        },
        submitTwit() {
            if (!this.text || !this.author) {
                this.errorMessage();
            } else {
                //console.log('We have submitted stuff', this.author, this.text)
                //this.$emit('text', this.text);
                //this.$emit('author', this.author)
                let newTwit = {
                    text: this.text,
                    author: this.author,
                };
                this.$emit("addTwit", newTwit);
                this.closeModal();
            }
        },
    },
    data() {
        return {
            text: "",
            author: "",
        };
    },
};
</script>

<template>
    <div id="modal-backdrop" class="hidden"></div>
    <div id="create-twit-modal" class="hidden">
        <div class="modal-dialog">
            <div class="modal-header">
                <h3>Create a Twit</h3>
                <button
                    type="button"
                    class="modal-close-button"
                    @click="closeModal"
                >
                    &times;
                </button>
            </div>

            <div class="modal-body">
                <div class="twit-input-element">
                    <label for="twit-text-input">Twit text</label>
                    <textarea id="twit-text-input" v-model="text"></textarea>
                </div>
                <div class="twit-input-element">
                    <label for="twit-author-input">Author</label>
                    <input
                        type="text"
                        id="twit-author-input"
                        v-model="author"
                    />
                </div>
            </div>

            <div class="modal-footer">
                <button
                    type="button"
                    class="modal-cancel-button"
                    @click="closeModal"
                >
                    Cancel
                </button>
                <button
                    type="button"
                    class="modal-accept-button"
                    @click="submitTwit"
                >
                    Create Twit
                </button>
            </div>
        </div>
    </div>
</template>

<style>
#create-twit-button {
    position: fixed;
    right: 30px;
    bottom: 30px;
    height: 60px;
    width: 60px;
    border: none;
    border-radius: 30px;
    font-size: 30px;
    background-color: #ff1010;
    color: #fff;
    cursor: pointer;
    box-shadow: 4px 4px 12px rgba(0, 0, 0, 0.25);
}

#create-twit-button:hover,
#create-twit-button:focus {
    right: 27px;
    bottom: 27px;
    height: 66px;
    width: 66px;
    border-radius: 33px;
    font-size: 36px;
    background-color: #319df6;
}

#create-twit-button:focus {
    outline: none;
}

#modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    background-color: rgba(0, 0, 0, 0.85);
}

#create-twit-modal {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 1010;
    overflow: scroll;
}

/*.hidden {
    display: none;
}*/

.modal-dialog {
    width: auto;
    max-width: 600px;
    min-width: 350px;
    min-height: 300px;
    margin: 40px auto;
    background-color: #fff;
    border-radius: 15px;
}

.modal-header {
    position: relative;
    padding: 10px 20px;
}

.modal-header h3 {
    margin: 0;
    font-size: 28px;
}

.modal-close-button {
    position: absolute;
    right: 10px;
    top: 5px;
    font-size: 24px;
    border: none;
    background: none;
    padding: 0;
    cursor: pointer;
}

.modal-body {
    padding: 20px;
}

.twit-input-element {
    display: flex;
    align-items: center;
    font-size: 20px;
    margin: 10px 0;
}

.twit-input-element label {
    font-weight: 600;
    flex: 1 75px;
    margin-right: 10px;
}

.twit-input-element input,
.twit-input-element textarea {
    flex: 6 200px;
    padding: 8px;
    font-size: 20px;
    border: 1px solid #aaa;
}

.twit-input-element textarea {
    min-height: 64px;
}

.modal-footer {
    display: flex;
    justify-content: flex-end;
    padding: 10px 10px 20px 10px;
}

.modal-footer button {
    font-size: 20px;
    background-color: #fff;
    color: #333;
    border: 1px solid #333;
    border-radius: 5px;
    padding: 10px;
    margin-right: 20px;
    cursor: pointer;
}

.modal-footer .modal-cancel-button:hover {
    background-color: #eee;
}

.modal-footer .modal-accept-button {
    background-color: #319df6;
    color: #fff;
}

.modal-footer .modal-accept-button:hover {
    background-color: #087dde;
}

.error-container {
    margin-top: 50px;
    text-align: center;
}

.error-container h2 {
    margin: 10px 0;
    font-size: 96px;
    font-weight: 100;
}

.error-container h3 {
    margin: 10px 0;
    font-size: 36px;
    font-weight: 400;
}
</style>
