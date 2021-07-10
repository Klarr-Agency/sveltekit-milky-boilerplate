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
            background-color: #262626;
            border-radius: 18px;
            border: 3px solid transparent;
            padding: 4px 16px;
            height: 38px;
            &:focus {
                outline: 0;
                border: 3px solid red;
            }
        }
    }
</style>