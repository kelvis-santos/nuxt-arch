<template>
  <div class="container-error">
    <p class="error-messege">
        {{ errorMsg }}
    </p>
  </div>
</template>

<script>
export default {
    name: 'error-card',

    props: {
        errorMsg: {
            type: String,
            required: false,
            default: 'Erro!'
        }
    }
}
</script>

<style>
    .container-error {
        display: flex;
        background-color: #de8071;
        width: 80%;
        height: 3rem;
        justify-content: center;
        align-items: center;
        margin-left: 2.5rem;
    }
    .error-messege {
        text-align: center;
        display: flex;
        color: white;
    }
</style>