<script>
    import { onMount, onDestroy } from "svelte";
    import { inertia, useForm } from "@inertiajs/inertia-svelte";

    import SubLayout from "@/DashboardLayouts/SubLayout.svelte";
    import { loadScript } from "@/helpers/document.js";
    onMount(async () => {
        let checkload = setInterval(async () => {
            if (window.jQuery && window.DataTable) {
                clearInterval(checkload);
            }
        }, 1000);
    });

    onDestroy(() => {
        // document?.querySelector(".dataTables_wrapper")?.remove();
    });

    let form = useForm({
        name: null,
        email: null,
    });
    function submit() {
        $form.post("/yuran", {
            onSuccess: () => $form.reset(),
        });
    }
    export let errors = {};
    let closeEle = (e) => {
        errors = {};
    };
</script>

<svelte:head>
    <title>Yuran</title>
</svelte:head>

<SubLayout>
    <!-- Container-fluid starts-->
    <div class="container-fluid dashboard-default-sec">
        <div class="row">
            <div class="col-sm-12">
                <div class="card">
                    <form class="theme-form" on:submit|preventDefault={submit}>
                        <div class="card-header pb-0">
                            <h5>Create Yuran</h5>
                        </div>
                        <div class="card-body">
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

                            <div class="mb-3">
                                <label
                                    class="col-form-label pt-0"
                                    for="exampleInputEmail1"
                                    >Email address</label
                                >
                                <input
                                    class="form-control"
                                    id="exampleInputEmail1"
                                    type="text"
                                    aria-describedby="emailHelp"
                                    placeholder="Enter email"
                                    bind:value={$form.name}
                                /><small
                                    class="form-text text-muted"
                                    id="emailHelp"
                                    >We'll never share your email with anyone
                                    else.</small
                                >
                            </div>
                            <div class="mb-3">
                                <label
                                    class="col-form-label pt-0"
                                    for="exampleInputPassword1">Password</label
                                >
                                <input
                                    class="form-control"
                                    id="exampleInputPassword1"
                                    type="email"
                                    placeholder="Password"
                                    bind:value={$form.email}
                                />
                            </div>
                        </div>
                        <div class="card-footer">
                            <button class="btn btn-primary">Submit</button>
                            <button
                                use:inertia={{ href: "/yuran", method: "get" }}
                                class="btn btn-secondary">Cancel</button
                            >
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
    <!-- Container-fluid Ends-->
</SubLayout>
