<script>
    import { onMount, tick } from "svelte";
    import { loadScript } from "@/helpers/document.js";
    import BreezeButton from "@/Components/Button.svelte";
    import BreezeGuestLayout from "@/Layouts/Guest.svelte";
    import BreezeInput from "@/Components/Input.svelte";
    import BreezeLabel from "@/Components/Label.svelte";
    import BreezeValidationErrors from "@/Components/ValidationErrors.svelte";
    import SubLayout from "@/NewLayouts/SubLayout.svelte";

    import { inertia, useForm } from "@inertiajs/inertia-svelte";

    onMount(async () => {
        let checkload = setInterval(async () => {
            if (window.jQuery) {
                // console.log("script loaded successfully!");
                clearInterval(checkload);
            }
        }, 1000);
    });

    let form = useForm({
        name: null,
        email: null,
        password: null,
        password_confirmation: null,
        agree: null,
    });

    function submit() {
        $form.post("/register");
    }
    export let errors = {};
    let closeEle = (e) => {
        errors = {};
    };
</script>

<svelte:head>
    <title>Register</title>
</svelte:head>

<SubLayout>
    <section class="pt-5">
        <div class="container-fluid p-0">
            <div class="row m-0">
                <div class="col-xl-5">
                    <img
                        class="bg-img-cover bg-center"
                        src="/assets/images/login/3.jpg"
                        alt="loginpage"
                    />
                </div>
                <div class="col-xl-7 p-0">
                    <div class="login-card">
                        <form
                            class="theme-form login-form"
                            on:submit|preventDefault={submit}
                        >
                            <h4>Create your account</h4>
                            <h6>
                                Enter your personal details to create account
                            </h6>
                            {#if Object.keys(errors).length > 0}
                                <div
                                    class="alert alert-danger alert-dismissible fade show"
                                    role="alert"
                                >
                                    {errors?.[Object.keys(errors)[0]]}

                                    <button
                                        on:click={(e) => closeEle(e)}
                                        type="button"
                                        class="btn-close"
                                        data-bs-dismiss="alert"
                                        aria-label="Close"
                                    />
                                </div>
                            {/if}

                            <div class="form-group">
                                <label>Your Name</label>

                                <div class="input-group">
                                    <span class="input-group-text"
                                        ><i class="icon-user" /></span
                                    >
                                    <input
                                        id="name"
                                        type="text"
                                        class="form-control"
                                        bind:value={$form.name}
                                        required
                                        autofocus
                                        placeholder="Full Name"
                                        autocomplete="name"
                                    />
                                </div>
                            </div>
                            <div class="form-group">
                                <label>Email Address</label>
                                <div class="input-group">
                                    <span class="input-group-text"
                                        ><i class="icon-email" /></span
                                    >
                                    <input
                                        class="form-control"
                                        id="email"
                                        type="email"
                                        bind:value={$form.email}
                                        required
                                        placeholder="Test@gmail.com"
                                    />
                                </div>
                            </div>
                            <div class="form-group">
                                <label>Password</label>
                                <div class="input-group">
                                    <span class="input-group-text"
                                        ><i class="icon-lock" /></span
                                    >
                                    <input
                                        id="password"
                                        bind:value={$form.password}
                                        required
                                        class="form-control"
                                        type="password"
                                        placeholder="*********"
                                    />
                                </div>
                            </div>
                            <div class="form-group">
                                <label>Confirm Password</label>
                                <div class="input-group">
                                    <span class="input-group-text"
                                        ><i class="icon-lock" /></span
                                    >
                                    <input
                                        id="password_confirmation"
                                        type="password"
                                        class="form-control"
                                        bind:value={$form.password_confirmation}
                                        required
                                        placeholder="*********"
                                    />
                                </div>
                            </div>
                            <div class="form-group">
                                <div class="checkbox">
                                    <input
                                        id="agree"
                                        type="checkbox"
                                        required
                                        bind:checked={$form.agree}
                                    />
                                    <label class="text-muted" for="agree"
                                        >Agree with <span>
                                            Privacy Policy</span
                                        ></label
                                    >
                                </div>
                            </div>
                            <div class="form-group">
                                <button
                                    class="btn btn-primary btn-block"
                                    type="submit"
                                    disabled={$form.processing}>Register</button
                                >
                            </div>
                            <!-- <div class="login-social-title">
                                <h5>Sign in with</h5>
                            </div>
                            <div class="form-group">
                                <ul class="login-social">
                                    <li>
                                        <a
                                            href="https://www.linkedin.com/login"
                                            target="_blank"
                                            ><i data-feather="linkedin" /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            href="https://www.linkedin.com/login"
                                            target="_blank"
                                            ><i data-feather="twitter" /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            href="https://www.linkedin.com/login"
                                            target="_blank"
                                            ><i data-feather="facebook" /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            href="https://www.instagram.com/login"
                                            target="_blank"
                                            ><i data-feather="instagram" /></a
                                        >
                                    </li>
                                </ul>
                            </div> -->
                            <p>
                                Already have an account?<a
                                    class="ms-2"
                                    href="/login"
                                    use:inertia>Sign in</a
                                >
                            </p>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>
</SubLayout>
