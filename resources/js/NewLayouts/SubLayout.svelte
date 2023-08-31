<script>
    import Layout from "@/NewLayouts/Layout.svelte";
    import Navbar from "@/NewLayouts/Navbar.svelte";
</script>

<svelte:head>
    <title>Welcome</title>
</svelte:head>

<Layout>
    <body class="landing-wrraper">
        <!-- Loader starts-->
        <div class="loader-wrapper">
            <div class="theme-loader">
                <div class="loader-p" />
            </div>
        </div>
        <!-- Loader ends-->

        <!-- tap on top starts-->
        <div class="tap-top"><i data-feather="chevrons-up" /></div>
        <!-- tap on tap ends-->
        <!-- page-wrapper Start-->
        <div class="page-wrapper landing-page">
            <!-- Page Body Start-->
            <div class="page-body-wrapper">
                <Navbar />
                <slot />

                <!--footer start-->
                <div class="sub-footer">
                    <div class="custom-container">
                        <div class="row">
                            <div class="col-md-6 col-sm-2">
                                <div class="footer-contain">
                                    <img
                                        class="img-fluid"
                                        src="../assets/images/logo/logo.png"
                                        alt=""
                                    />
                                </div>
                            </div>
                            <div class="col-md-6 col-sm-10">
                                <div class="footer-contain">
                                    <p class="mb-0">
                                        Copyright 2023-24 © 4in44 All rights
                                        reserved.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!--footer end-->
            </div>
        </div>

        <!-- login js-->
        <!-- Plugin used-->
    </body>
</Layout>
