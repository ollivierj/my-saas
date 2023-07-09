<section class="section-container">
    <h1 class="headline">{heading}</h1>
    {#if !submitted && !error}
        <form on:submit|preventDefault={submit_form}>
            <label>
                <input
                        required
                        name="vatnumber"
                        type="text"
                        placeholder={form.placeholder} />
            </label>
            <button class="button" type="submit">
                {#if !submitting}
                    {form.button_label}
                {:else}
                    <Icon icon="eos-icons:loading" />
                {/if}
            </button>
        </form>
    {:else if submitted}
        <div class="message" in:fade>{form.success_message}</div>
    {:else if error}
        <div class="message error" in:fade>{form.error_message}</div>
    {/if}
</section>
