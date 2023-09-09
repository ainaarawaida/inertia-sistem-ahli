<script>
    import { onMount, tick } from "svelte";
    import { loadScript } from "@/helpers/document.js";
    import BreezeButton from "@/Components/Button.svelte";
    import BreezeGuestLayout from "@/Layouts/Guest.svelte";
    import BreezeInput from "@/Components/Input.svelte";
    import BreezeLabel from "@/Components/Label.svelte";
    import BreezeValidationErrors from "@/Components/ValidationErrors.svelte";
    import SubLayout from "@/NewLayouts/SubLayout.svelte";

    import { inertia, useForm, page } from "@inertiajs/inertia-svelte";

    onMount(async () => {
        // console.log(window.location.origin);
        let checkload = setInterval(async () => {
            if (window.jQuery && window.$) {
                let getselect2 = window.$(".jsselect2").select2();
                getselect2.on("select2:select", function (e) {
                    $form.negeri = e.target.value;
                });

                // console.log("script loaded successfully!");
                clearInterval(checkload);
            }
        }, 1000);
    });

    let form = useForm({
        name: null,
        email: null,
        password: null,
        agree: null,
        name_organisasi: null,
        email_organisasi: null,
        logo_organisasi: null,
        alamat: null,
        bandar: null,
        negeri: null,
        url: "",
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
    <br /><br /><br /><br />
    <div class="m-3 p-3">
        <div class="card p-5">
            <form class="" on:submit|preventDefault={submit}>
                <div class="row">
                    <div class="col">
                        <div class="card">
                            <div class="card-header pb-0">
                                <h5>Maklumat Admin</h5>
                            </div>
                            <div class="card-body">
                                <div class="form-group">
                                    <label>Nama</label>

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
                                            placeholder="Nama Penuh"
                                            autocomplete="name"
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Emel</label>
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
                                    <label>Jawatan</label>
                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i
                                                class="icofont icofont-flame-torch"
                                            /></span
                                        >
                                        <input
                                            id="jawatan"
                                            bind:value={$form.jawatan}
                                            required
                                            class="form-control"
                                            type="jawatan"
                                            placeholder=""
                                        />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card">
                            <div class="card-header pb-0">
                                <h5>Maklumat Organisasi</h5>
                            </div>
                            <div class="card-body">
                                <div class="form-group">
                                    <label>Nama Organisasi</label>

                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i class="icon-user" /></span
                                        >
                                        <input
                                            id="name_organisasi"
                                            type="text"
                                            class="form-control"
                                            bind:value={$form.name_organisasi}
                                            required
                                            placeholder="Nama Organisasi "
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Emel Organisasi</label>
                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i class="icon-email" /></span
                                        >
                                        <input
                                            class="form-control"
                                            id="email_organisasi"
                                            type="email"
                                            bind:value={$form.email_organisasi}
                                            required
                                            placeholder="Test@gmail.com"
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Logo Organisasi</label>
                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i class="icon-save-alt" /></span
                                        >
                                        <input
                                            class="form-control"
                                            id="logo_organisasi"
                                            type="file"
                                            bind:value={$form.logo_organisasi}
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Alamat</label>
                                    <div class="input-group">
                                        <textarea
                                            class="form-control"
                                            id="alamat"
                                            bind:value={$form.alamat}
                                            required
                                            rows="2"
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Bandar</label>
                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i class=" icon-direction" /></span
                                        >
                                        <input
                                            id="bandar"
                                            bind:value={$form.bandar}
                                            required
                                            class="form-control"
                                            type="bandar"
                                            placeholder=""
                                        />
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Negeri</label>
                                    <div class="input-group">
                                        <select
                                            bind:value={$form.negeri}
                                            class="form-control jsselect2"
                                            required
                                        >
                                            <option value="">Pilih</option>
                                            <option value="Johor">Johor</option>
                                            <option value="Kedah">Kedah</option>
                                            <option value="Kelantan"
                                                >Kelantan</option
                                            >
                                            <option value="Kuala Lumpur"
                                                >Kuala Lumpur</option
                                            >
                                            <option value="Labuan"
                                                >Labuan</option
                                            >
                                            <option value="Melaka"
                                                >Melaka</option
                                            >
                                            <option value="Negeri Sembilan"
                                                >Negeri Sembilan</option
                                            >
                                            <option value="Pahang"
                                                >Pahang</option
                                            >
                                            <option value="Penang"
                                                >Penang</option
                                            >
                                            <option value="Perak">Perak</option>
                                            <option value="Perlis"
                                                >Perlis</option
                                            >
                                            <option value="Putrajaya"
                                                >Putrajaya</option
                                            >
                                            <option value="Sabah">Sabah</option>
                                            <option value="Sarawak"
                                                >Sarawak</option
                                            >
                                            <option value="Selangor"
                                                >Selangor</option
                                            >
                                            <option value="Terengganu"
                                                >Terengganu</option
                                            >
                                        </select>
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label>Url Page</label>
                                    <div class="input-group">
                                        <span class="input-group-text"
                                            ><i class="icon-world" /></span
                                        >
                                        <input
                                            id="url"
                                            bind:value={$form.url}
                                            required
                                            class="form-control"
                                            type="url"
                                            placeholder=""
                                        />
                                    </div>
                                    <span
                                        >{window.location
                                            .origin}/{$form.url}</span
                                    >
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="form-group">
                        <div class="checkbox">
                            <input
                                id="agree"
                                type="checkbox"
                                required
                                bind:checked={$form.agree}
                            />
                            <label class="text-muted" for="agree"
                                >Agree with <span> Privacy Policy</span></label
                            >
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="card-footer">
                        <button
                            class="btn btn-primary float-end m-1"
                            type="submit"
                            disabled={$form.processing}>Register</button
                        >

                        <a
                            use:inertia
                            href="/"
                            class="btn btn-secondary float-end m-1">Cancel</a
                        >
                    </div>
                </div>
            </form>
        </div>
    </div>
</SubLayout>
