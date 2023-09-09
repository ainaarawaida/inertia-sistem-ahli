<script>
    import { onMount } from "svelte";
    import { loadScript } from "@/helpers/document.js";

    onMount(async () => {
        await loadScript(
            "/assets/js/jquery-3.5.1.min.js",
            "jquery-3.5.1.min.js"
        );
        await loadScript(
            "/assets/js/icons/feather-icon/feather.min.js",
            "feather.min.js"
        );
        await loadScript(
            "/assets/js/icons/feather-icon/feather-icon.js",
            "feather-icon.js"
        );
        await loadScript("/assets/js/sidebar-menu.js", "sidebar-menu.js");
        await loadScript("/assets/js/config.js", "config.js");
        await loadScript("/assets/js/bootstrap/popper.min.js", "popper.min.js");
        await loadScript(
            "/assets/js/bootstrap/bootstrap.min.js",
            "bootstrap.min.js"
        );

        // await loadScript(
        //     "/assets/js/owlcarousel/owl.carousel.js",
        //     "owl.carousel.js"
        // );
        // await loadScript(
        //     "/assets/js/owlcarousel/owl-custom.js",
        //     "owl-custom.js"
        // );
        // await loadScript("/assets/js/landing_sticky.js", "landing_sticky.js");
        // await loadScript("/assets/js/landing.js", "landing.js");

        // await loadScript("/assets/js/jarallax_libs/libs.min.js", "libs.min.js");

        await loadScript(
            "/assets/js/chart/chartjs/chart.min.js",
            "chart.min.js"
        );
        await loadScript(
            "/assets/js/chart/chartist/chartist.js",
            "chartist.js"
        );
        await loadScript(
            "/assets/js/chart/chartist/chartist-plugin-tooltip.js",
            "chartist-plugin-tooltip.js"
        );
        await loadScript("/assets/js/chart/knob/knob.min.js", "knob.min.js");
        await loadScript(
            "/assets/js/chart/knob/knob-chart.js",
            "knob-chart.js"
        );
        await loadScript(
            "/assets/js/chart/apex-chart/apex-chart.js",
            "apex-chart.js"
        );
        await loadScript(
            "/assets/js/chart/apex-chart/stock-prices.js",
            "stock-prices.js"
        );
        await loadScript("/assets/js/prism/prism.min.js", "prism.min.js");
        await loadScript(
            "/assets/js/clipboard/clipboard.min.js",
            "clipboard.min.js"
        );
        await loadScript(
            "/assets/js/counter/jquery.waypoints.min.js",
            "jquery.waypoints.min.js"
        );
        await loadScript(
            "/assets/js/counter/jquery.counterup.min.js",
            "jquery.counterup.min.js"
        );
        await loadScript(
            "/assets/js/counter/counter-custom.js",
            "counter-custom.js"
        );
        await loadScript(
            "/assets/js/custom-card/custom-card.js",
            "custom-card.js"
        );
        await loadScript(
            "/assets/js/notify/bootstrap-notify.min.js",
            "bootstrap-notify.min.js"
        );
        await loadScript(
            "/assets/js/vector-map/jquery-jvectormap-2.0.2.min.js",
            "jquery-jvectormap-2.0.2.min.js"
        );
        await loadScript(
            "/assets/js/vector-map/map/jquery-jvectormap-world-mill-en.js",
            "jquery-jvectormap-world-mill-en.js"
        );
        await loadScript(
            "/assets/js/vector-map/map/jquery-jvectormap-in-mill.js",
            "jquery-jvectormap-in-mill.js"
        );
        await loadScript(
            "/assets/js/vector-map/map/jquery-jvectormap-asia-mill.js",
            "jquery-jvectormap-asia-mill.js"
        );
        await loadScript("/assets/js/dashboard/default.js", "default.js");
        await loadScript("/assets/js/notify/index.js", "index.js");
        await loadScript(
            "/assets/js/datepicker/date-picker/datepicker.js",
            "datepicker.js"
        );
        await loadScript(
            "/assets/js/datepicker/date-picker/datepicker.en.js",
            "datepicker.en.js"
        );
        await loadScript(
            "/assets/js/datepicker/date-picker/datepicker.custom.js",
            "datepicker.custom.js"
        );
        await loadScript("/assets/js/script.js", "script.js");
        // await loadScript(
        //     "/assets/js/theme-customizer/customizer.js",
        //     "customizer.js"
        // );

        await loadScript(
            "/assets/js/datatable/datatables/jquery.dataTables.min.js",
            "jquery.dataTables.min.js"
        );

        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.buttons.min.js",
            "dataTables.buttons.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/jszip.min.js",
            "jszip.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/buttons.colVis.min.js",
            "buttons.colVis.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/pdfmake.min.js",
            "pdfmake.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/vfs_fonts.js",
            "vfs_fonts.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.autoFill.min.js",
            "dataTables.autoFill.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.select.min.js",
            "dataTables.select.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/buttons.bootstrap4.min.js",
            "buttons.bootstrap4.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/buttons.html5.min.js",
            "buttons.html5.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/buttons.print.min.js",
            "buttons.print.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.bootstrap4.min.js",
            "dataTables.bootstrap4.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.responsive.min.js",
            "dataTables.responsive.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/responsive.bootstrap4.min.js",
            "responsive.bootstrap4.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.keyTable.min.js",
            "dataTables.keyTable.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.colReorder.min.js",
            "dataTables.colReorder.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.fixedHeader.min.js",
            "dataTables.fixedHeader.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.rowReorder.min.js",
            "dataTables.rowReorder.min.js"
        );
        await loadScript(
            "/assets/js/datatable/datatable-extension/dataTables.scroller.min.js",
            "dataTables.scroller.min.js"
        );
        await loadScript("/assets/js/tooltip-init.js", "tooltip-init.js");
        await loadScript(
            "https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/js/toastr.min.js",
            "toastr.min.js"
        );

        let checkload = setInterval(async () => {
            if (window.jQuery && window.DataTable) {
                console.log("script loaded successfully!");

                clearInterval(checkload);
            }
        }, 1000);
    });
</script>

<svelte:head>
    <meta name="description" content="Sistem Ahli" />
    <meta name="keywords" content="Sistem Ahli" />
    <meta name="author" content="pixelstrap" />
    <link rel="icon" href="/assets/images/favicon.png" type="image/x-icon" />
    <link
        rel="shortcut icon"
        href="/assets/images/favicon.png"
        type="image/x-icon"
    />
    <title>Sistem Ahli - Welcome</title>

    <!-- Font Awesome-->
    <link rel="stylesheet" type="text/css" href="/assets/css/fontawesome.css" />
    <!-- ico-font-->
    <link rel="stylesheet" type="text/css" href="/assets/css/icofont.css" />
    <!-- Themify icon-->
    <link rel="stylesheet" type="text/css" href="/assets/css/themify.css" />
    <!-- Flag icon-->
    <link rel="stylesheet" type="text/css" href="/assets/css/flag-icon.css" />
    <!-- Feather icon-->
    <link
        rel="stylesheet"
        type="text/css"
        href="/assets/css/feather-icon.css"
    />
    <!-- Plugins css start-->
    <link rel="stylesheet" type="text/css" href="/assets/css/animate.css" />
    <link rel="stylesheet" type="text/css" href="/assets/css/chartist.css" />
    <link rel="stylesheet" type="text/css" href="/assets/css/date-picker.css" />
    <link rel="stylesheet" type="text/css" href="/assets/css/prism.css" />
    <link rel="stylesheet" type="text/css" href="/assets/css/vector-map.css" />
    <link rel="stylesheet" type="text/css" href="/assets/css/owlcarousel.css" />

    <!-- Plugins css Ends-->
    <!-- Bootstrap css-->
    <link rel="stylesheet" type="text/css" href="/assets/css/bootstrap.css" />
    <!-- App css-->
    <link rel="stylesheet" type="text/css" href="/assets/css/style.css" />
    <link
        id="color"
        rel="stylesheet"
        href="/assets/css/color-1.css"
        media="screen"
    />
    <!-- Responsive css-->
    <link rel="stylesheet" type="text/css" href="/assets/css/responsive.css" />

    <link rel="stylesheet" type="text/css" href="/assets/css/datatables.css" />
    <link
        rel="stylesheet"
        type="text/css"
        href="/assets/css/datatable-extension.css"
    />

    <link
        rel="stylesheet"
        type="text/css"
        href="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/toastr.min.css"
    />
</svelte:head>

<slot />
