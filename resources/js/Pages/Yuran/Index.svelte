<script>
    import { onMount, onDestroy } from "svelte";
    import { Inertia } from "@inertiajs/inertia";

    import SubLayout from "@/DashboardLayouts/SubLayout.svelte";
    import { loadScript } from "@/helpers/document.js";
    onMount(async () => {
        let checkload = setInterval(async () => {
            if (window.jQuery && window.DataTable) {
                new DataTable("#example", {
                    dom: "Bfrtip",
                    buttons: [
                        {
                            text: "Add New",
                            className: "btn-success",
                            action: function (e, dt, node, config) {
                                Inertia.visit("/yuran/create", {
                                    method: "get",
                                });
                            },
                        },
                    ],

                    searchDelay: 2000,
                    ajax: "/yuran",
                    processing: true,
                    serverSide: true,
                    columns: [
                        { data: "id" },
                        { data: "name" },
                        { data: "email" },
                        { data: "created_at" },
                        { data: "action" },
                    ],
                });

                document
                    ?.querySelector("#example")
                    ?.addEventListener("click", (e) => {
                        let ele = e.target
                            .closest(".edit")
                            .getAttribute("data-id");

                        Inertia.visit("/yuran/1/edit", { method: "get" });
                    });
                clearInterval(checkload);
            }
        }, 1000);
    });

    onDestroy(() => {
        document?.querySelector(".dataTables_wrapper")?.remove();
    });
</script>

<svelte:head>
    <title>Yuran</title>
</svelte:head>

<SubLayout>
    <!-- Container-fluid starts-->
    <div class="container-fluid dashboard-default-sec">
        <div class="row">
            <table id="example" class="display" style="width:100%">
                <thead>
                    <tr>
                        <th>ID</th>
                        <th>Name</th>
                        <th>Email</th>
                        <th>Created At</th>
                        <th>Action</th>
                    </tr>
                </thead>
            </table>
        </div>
    </div>
    <!-- Container-fluid Ends-->
</SubLayout>
