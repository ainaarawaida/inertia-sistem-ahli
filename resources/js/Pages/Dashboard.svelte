<script>
    import { onMount } from "svelte";
    import { page } from "@inertiajs/inertia-svelte";
    import SubLayout from "@/DashboardLayouts/SubLayout.svelte";
    import { loadScript } from "@/helpers/document.js";
    import Toastr from "@/helpers/Toastr.svelte";
    export let message;

    console.log("message", message);
    onMount(async () => {
        let checkload = setInterval(async () => {
            if (window.jQuery) {
                await loadScript(
                    "/assets/js/dashboard/dashboard_2.js",
                    "dashboard_2.js"
                );

                clearInterval(checkload);
            }
        }, 1000);
    });
</script>

<svelte:head>
    <title>Dashboard</title>
</svelte:head>

<SubLayout>
    <Toastr {message} />
    <!-- Container-fluid starts-->
    <div class="container-fluid dashboard-default-sec">
        <div class="row">
            <div class="col-lg-3 col-xs-6">
                <!-- small box -->
                <div class="card income-card card-primary">
                    <div class="card-body">
                        <div class="round-progress knob-block text-center">
                            <div class="progress-circle">
                                <input
                                    class="knob1"
                                    data-width="50"
                                    data-height="70"
                                    data-thickness=".3"
                                    data-fgcolor="#24695c"
                                    data-linecap="round"
                                    data-angleoffset="0"
                                    value="60"
                                />
                            </div>
                            <h5>$4,55,462</h5>
                            <p>Jumlah Bayaran (RM)</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-3 col-xs-6">
                <!-- small box -->
                <div class="card income-card card-primary">
                    <div class="card-body">
                        <div class="round-progress knob-block text-center">
                            <div class="progress-circle">
                                <input
                                    class="knob1"
                                    data-width="50"
                                    data-height="70"
                                    data-thickness=".3"
                                    data-fgcolor="#24695c"
                                    data-linecap="round"
                                    data-angleoffset="0"
                                    value="60"
                                />
                            </div>
                            <h5>$4,55,462</h5>
                            <p>Jumlah Tunggakan (RM)</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-3 col-xs-6">
                <!-- small box -->
                <div class="card income-card card-primary">
                    <div class="card-body">
                        <div class="round-progress knob-block text-center">
                            <div class="progress-circle">
                                <input
                                    class="knob1"
                                    data-width="50"
                                    data-height="70"
                                    data-thickness=".3"
                                    data-fgcolor="#24695c"
                                    data-linecap="round"
                                    data-angleoffset="0"
                                    value="60"
                                />
                            </div>
                            <h5>$4,55,462</h5>
                            <p>Permohonan Baru</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-3 col-xs-6">
                <!-- small box -->
                <div class="card income-card card-primary">
                    <div class="card-body">
                        <div class="round-progress knob-block text-center">
                            <div class="progress-circle">
                                <input
                                    class="knob1"
                                    data-width="50"
                                    data-height="70"
                                    data-thickness=".3"
                                    data-fgcolor="#24695c"
                                    data-linecap="round"
                                    data-angleoffset="0"
                                    value="60"
                                />
                            </div>
                            <h5>$4,55,462</h5>
                            <p>Ahli Berdaftar (Aktif)</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- Container-fluid Ends-->
</SubLayout>
