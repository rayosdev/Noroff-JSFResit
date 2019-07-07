<template>
    <div class="main-container">
        <form action="" class="contact-form__container">

            <label class="contact-form__name" for="name">
                <input type="text" id="name" class="contact-form__name-input">
            </label>
            <label class="contact-form__phone" for="phone">
                <input type="text" id="phone" class="contact-form__phone-input">
            </label>
            <label for="phone">
                <select>
                    <option value="volvo">Enquiry</option>
                    <option value="saab">Complaint</option>
                    <option value="mercedes">Compliment</option>
                    <option value="audi">General Message</option>
                </select>
            </label>

        </form>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="stylus" scoped>

</style>