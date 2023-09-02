<script>
    import { inertia, page, Link } from "@inertiajs/inertia-svelte";
    export let user = $page.props.auth.user;
</script>

<!-- Page Sidebar Start-->
<header class="main-nav">
    <div class="sidebar-user text-center">
        <a class="setting-primary" href="javascript:void(0)"
            ><i data-feather="settings" /></a
        ><img
            class="img-90 rounded-circle"
            src="/assets/images/dashboard/1.png"
            alt=""
        />
        <div class="badge-bottom">
            <span class="badge badge-primary">New</span>
        </div>
        <a href="user-profile.html">
            <h6 class="mt-3 f-14 f-w-600">{user.name}</h6>
        </a>
        <p class="mb-0 font-roboto">{user.email}</p>
    </div>
    <nav>
        <div class="main-navbar">
            <div class="left-arrow" id="left-arrow">
                <i data-feather="arrow-left" />
            </div>
            <div id="mainnav">
                <ul class="nav-menu custom-scrollbar">
                    <li class="back-btn">
                        <div class="mobile-back text-end">
                            <span>Back</span><i
                                class="fa fa-angle-right ps-2"
                                aria-hidden="true"
                            />
                        </div>
                    </li>

                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/dashboard"
                            ><i data-feather="home" /><span>Dashboard</span></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/yuran"
                            ><i data-feather="airplay" /><span>Yuran</span></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/senarai-ahli"
                            ><i data-feather="layout" /><span>Senarai Ahli</span
                            ></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/rekod-bayaran"
                            ><i data-feather="layout" /><span
                                >Rekod Bayaran</span
                            ></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/laporan"
                            ><i data-feather="layout" /><span>Laporan</span></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/makluman"
                            ><i data-feather="layout" /><span>Makluman</span></a
                        >
                    </li>
                    <li class="dropdown">
                        <a
                            use:inertia
                            class="nav-link menu-title link-nav"
                            href="/Setting"
                            ><i data-feather="layout" /><span>Setting</span></a
                        >
                    </li>
                    <li class="dropdown">&nbsp</li>
                    <li class="dropdown">&nbsp</li>
                </ul>
            </div>
            <div class="right-arrow" id="right-arrow">
                <i data-feather="arrow-right" />
            </div>
        </div>
    </nav>
</header>
<!-- Page Sidebar Ends-->
