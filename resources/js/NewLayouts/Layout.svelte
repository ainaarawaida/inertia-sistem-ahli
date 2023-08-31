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
        // await loadScript(
        //     "/assets/js/sidebar-menu.js",
        //     "sidebar-menu.js"
        // );
        await loadScript("/assets/js/config.js", "config.js");
        await loadScript("/assets/js/bootstrap/popper.min.js", "popper.min.js");
        await loadScript(
            "/assets/js/bootstrap/bootstrap.min.js",
            "bootstrap.min.js"
        );
        await loadScript(
            "/assets/js/owlcarousel/owl.carousel.js",
            "owl.carousel.js"
        );
        await loadScript(
            "/assets/js/owlcarousel/owl-custom.js",
            "owl-custom.js"
        );
        await loadScript("/assets/js/landing_sticky.js", "landing_sticky.js");
        await loadScript("/assets/js/landing.js", "landing.js");

        await loadScript("/assets/js/jarallax_libs/libs.min.js", "libs.min.js");

        await loadScript("/assets/js/script.js", "script.js");

        let checkload = setInterval(() => {
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
</svelte:head>

<slot />
