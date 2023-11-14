<script setup lang="ts">
</script>

<template>
    <div class="contact">
        <div class="title">CONTACT</div>
        <div class="container">
            <form>
                <div class="names">
                    <input type="text" id="prenom" placeholder="Prénom">
                    <input type="text" id="nom" placeholder="Nom">
                </div>
                <input type="email" id="mail" placeholder="Adresse courriel">
                <textarea name="description" id="description" cols="30" rows="5" placeholder="Informations sur la demande"></textarea>
                <button>ENVOYER</button>
            </form>
        </div>
    </div>
</template>

<style scoped>
    form input, textarea {
        border: none;
        background-color: var(--color-secondary);
        color: var(--color-text);

        /* Description */
        font-family: Poppins;
        font-size: 0.875rem;
        font-style: normal;
        font-weight: 400;
        line-height: normal;

        width: 100%;
        border-radius: 10px;

        padding: 1rem;
    }

    form input:focus-visible, textarea:focus-visible {
        border: none;
        outline: none;
    }

    textarea {
        resize: none;
    }

    .container form {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    .names {
        display: flex;
        flex-direction: row;
        gap: 1rem;
    }



    form input {
        height: 50px;
    }

    .container {
        border: 3px;
        border-radius: 10px;
        border-color: var(--color-gold);
        border-style: solid;
        margin: 2rem;
        padding: 2rem;
    }

    .contact {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .title {
        color: var(--color-gold);
        font-family: Poppins;
        font-size: 2.25rem;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        letter-spacing: 0.675rem;
    }

    button {
        border: 3px;
        border-radius: 10px;
        border-color: var(--color-gold);
        border-style: solid;
        height: 45px;
        background-color: var(--color-background);

        color: var(--color-gold, #F27B00);
        text-align: center;
        font-family: Poppins;
        font-size: 1.5rem;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
        letter-spacing: 0.3rem;
    }

    button:hover {
        background-color: var(--color-primary);
        cursor: pointer;
    }

    button:focus {
        background-color: var(--color-secondary);
    }


</style>