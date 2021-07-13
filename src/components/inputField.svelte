<script>
    export let label = "label";
    export let type = "text";
</script>
<div class="inputField">
    <label for="{label}" class="inputField__label">{label}</label>
    <input id="{label}" type="{type}" class="inputField__input">
</div>
<style lang="scss">
    .inputField {
        display: flex;
        flex-direction: column;
        margin-bottom: 24px;
        width: 100%;
        &__label {
            color: #FCFCFC;
            font-size: 18px;
            font-family: 'Work Sans', sans-serif;
            font-weight: 400;
            margin-bottom: 8px;
        }
        &__input {
            background-color: #292B3A;
            border-radius: 12px;
            border: 1px solid #424453;
            color: #FFF;
            padding: 4px 16px;
            height: 43px;
            &:focus {
                outline: 0;
                border: 1px solid #D99C98;
            }
        }
    }
</style>