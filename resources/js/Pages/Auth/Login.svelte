<script>
    import SubLayout from "@/NewLayouts/SubLayout.svelte";
    import { inertia, useForm } from "@inertiajs/inertia-svelte";
    let form = useForm({
        email: null,
        password: null,
        remember: false,
    });
    function submit() {
        $form.post("/login", {
            onSuccess: () => $form.reset(),
        });
    }
    export let errors = {};
    let closeEle = (e) => {
        errors = {};
    };
</script>

<svelte:head>
    <title>Log in</title>
</svelte:head>

<SubLayout>
    <section>
        <div class="container-fluid">
            <div class="row">
                <div class="col-xl-7">
                    <img
                        class="bg-img-cover bg-center"
                        src="../assets/images/login/2.jpg"
                        alt="looginpage"
                    />
                </div>
                <div class="col-xl-5 p-0">
                    <div class="login-card">
                        <form
                            class="theme-form login-form"
                            on:submit|preventDefault={submit}
                        >
                            <h4>Login</h4>
                            <h6>Welcome back! Log in to your account.</h6>
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
                                <label>Email Address</label>
                                <div class="input-group">
                                    <span class="input-group-text"
                                        ><i class="icon-email" /></span
                                    >
                                    <input
                                        class="form-control"
                                        type="email"
                                        required=""
                                        placeholder="Test@gmail.com"
                                        bind:value={$form.email}
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
                                        class="form-control"
                                        type="password"
                                        name="login[password]"
                                        required=""
                                        placeholder="*********"
                                        bind:value={$form.password}
                                    />
                                    <div class="show-hide">
                                        <span class="show" />
                                    </div>
                                </div>
                            </div>
                            <div class="form-group">
                                <div class="checkbox">
                                    <input
                                        id="checkbox1"
                                        type="checkbox"
                                        bind:checked={form.remember}
                                    />
                                    <label class="text-muted" for="checkbox1"
                                        >Remember password</label
                                    >
                                </div>
                                <a
                                    class="link"
                                    use:inertia
                                    href="/password/reset">Forgot password?</a
                                >
                            </div>
                            <div class="form-group">
                                <button
                                    class="btn btn-primary btn-block"
                                    type="submit">Sign in</button
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
                                Don't have account?<a
                                    class="ms-2"
                                    href="sign-up.html">Create Account</a
                                >
                            </p>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>
</SubLayout>
