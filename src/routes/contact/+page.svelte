<article class="contact-form">
    <form method="post" action="https://formsubmit.co/alvisfranks@gmail.com">
        <label for="personName">Name*</label>
        <input type="text" id="personName" name="personName" required />

        <label for="email">E-mail*</label>
        <input type="email" name="email" id="email" required />

        <label for="phone">Phone number</label>
        <input type="tel" name="phone" id="phone" />

        <label for="offer-type">Choose one</label>
        <select name="offer-type" id="offer-type">
            <option value="">Job offer</option>
            <option value="">Project offer</option>
            <option value="">Other</option>
        </select>

        <label for="message">Your message*</label>
        <textarea name="message" id="message" required />

        <button type="submit">Submit</button>
    </form>
</article>

<style lang="scss">
    @import "src/global-colors.scss";
    .contact-form {
        background-color: $rich-black;
        display: flex;
        justify-content: center;

        form {
            display: flex;
            flex-direction: column;
            width: 100%;
            max-width: 500px;
            padding: 0 2rem;

            input,
            select {
                background-color: $rich-black;
                border: solid 1px $platinum;
                height: 30px;
                color: $platinum;
                font-family: Alata;
                vertical-align: baseline;
            }

            #message {
                min-height: 80px;
                background-color: $rich-black;
                border: solid 1px $platinum;
                color: $platinum;
                font-family: Alata;
            }

            label {
                color: $platinum;
                margin-bottom: 5px;
            }
            :nth-child(odd) {
                margin-top: 2rem;
            }

            select {
                color: $platinum;
                font-family: Alata;
            }

            button {
                display: inline-block;
                background-color: $rich-black;
                color: $platinum;
                height: 35px;
                border: solid 1px $platinum;
                font-family: Alata;
                cursor: pointer;
            }
        }
    }
</style>
