<script>
    import Layout from "@/DashboardLayouts/Layout.svelte";
    import Footer from "@/DashboardLayouts/Footer.svelte";
    import Navbar from "@/DashboardLayouts/Navbar.svelte";
    import Sidebar from "@/DashboardLayouts/Sidebar.svelte";
</script>

<svelte:head>
    <title>Welcome</title>
</svelte:head>

<Layout>
    <!-- Loader starts-->
    <div class="loader-wrapper">
        <div class="theme-loader">
            <div class="loader-p" />
        </div>
    </div>
    <!-- Loader ends-->
    <!-- page-wrapper Start       -->
    <div class="page-wrapper compact-wrapper" id="pageWrapper">
        <Navbar />
        <!-- Page Body Start-->
        <div class="page-body-wrapper sidebar-icon">
            <Sidebar />
            <div class="page-body">
                <!-- Container-fluid starts-->
                <slot />
                <!-- Container-fluid Ends-->
            </div>
            <Footer />
        </div>
    </div>
</Layout>
