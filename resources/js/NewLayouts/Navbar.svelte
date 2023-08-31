<script>
    import { inertia, Link, page } from "@inertiajs/inertia-svelte";
</script>

<!-- header start-->
<header class="landing-header">
    <div class="custom-container">
        <div class="row">
            <div class="col-12">
                <nav class="navbar navbar-light p-0" id="navbar-example2">
                    <a use:inertia class="navbar-brand" href="/">
                        <img
                            class="img-fluid"
                            src="/assets/images/logo/logo.png"
                            alt=""
                        /></a
                    >
                    <ul class="landing-menu nav nav-pills">
                        <li class="nav-item menu-back">
                            back<i class="fa fa-angle-right" />
                        </li>
                        <li class="nav-item">
                            <a use:inertia class="nav-link" href="/">Home</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#demo">Demo</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="/">Support</a>
                        </li>
                        <li class="nav-item">
                            <form class="form-inline" action="/">
                                <button class="nav-link">Hire Us</button>
                            </form>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="/">Document</a>
                        </li>
                    </ul>
                    <div class="buy-block">
                        <a use:inertia class="btn-landing" href="/register"
                            >Register</a
                        >&nbsp;
                        <a use:inertia class="btn-landing" href="/login"
                            >Login</a
                        >
                        <div class="toggle-menu">
                            <i class="fa fa-bars" />
                        </div>
                    </div>
                </nav>
            </div>
        </div>
    </div>
</header>
<!-- header end-->
