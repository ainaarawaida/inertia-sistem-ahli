<script>
    import SubLayout from "@/NewLayouts/SubLayout.svelte";
    import { onMount, onDestroy } from "svelte";
    import { Inertia } from "@inertiajs/inertia";

    import { loadScript } from "@/helpers/document.js";

    export let csrf_token;

    onMount(async () => {
        await loadScript(
            "https://code.jquery.com/jquery-3.7.0.js",
            "jquery-3.7.0.js"
        );

        await loadScript(
            "https://cdn.datatables.net/1.13.6/js/jquery.dataTables.min.js",
            "jquery.dataTables.min.js"
        );

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
                    ajax: {
                        url: "/",
                    },
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
    <title>Welcome</title>

    <link
        rel="stylesheet"
        type="text/css"
        href="https://cdn.datatables.net/1.13.6/css/jquery.dataTables.min.css"
    />
</svelte:head>

<SubLayout>
    <!--home section start-->
    <section class="landing-home section-pb-space" id="home">
        <div class="container pt-5 mt-5">
            <div class="card p-5">
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
            </div>
        </div>
        <!-- <img
            class="img-fluid bg-img-cover"
            src="../assets/images/landing/landing-home/home-bg2.jpg"
            alt=""
        />
        <div class="custom-container">
            <div class="row">
                <div class="col-12">
                    <div class="landing-home-contain">
                        <div>
                            <div class="landing-logo">
                                <img
                                    class="img-fluid"
                                    src="../assets/images/landing/landing-home/logo.png"
                                    alt=""
                                />
                            </div>
                            <h6>clean design</h6>
                            <h2>
                                viho Bootstrap <span>Admin Template</span>
                            </h2>
                            <p>
                                When it comes to dashboard or web apps. one of
                                the first impression you consider is the design.
                                It needs to be high quality enough otherwise you
                                will lose potential users due to bad design.
                            </p>
                            <div class="landing-button">
                                <a
                                    class="btn-landing btn-lg"
                                    href="index.html"
                                    target="_blank"
                                    ><img
                                        class="img-fluid"
                                        src="../assets/images/logo/html.png"
                                        alt=""
                                    />Html</a
                                ><a
                                    class="btn-landing btn-lg btn-secondary ms-2"
                                    href="https://react.pixelstrap.com/viho"
                                    target="_blank"
                                >
                                    <img
                                        class="img-fluid"
                                        src="../assets/images/logo/react.png"
                                        alt=""
                                    />React</a
                                ><a
                                    class="btn-landing btn-lg btn-success ms-2"
                                    href="https://laravel.pixelstrap.com/viho/dashboard"
                                    target="_blank"
                                    ><img
                                        class="img-fluid"
                                        src="../assets/images/logo/laravel.png"
                                        alt=""
                                    />Laravel</a
                                ><a
                                    class="btn-landing btn-lg btn-info ms-2"
                                    href="https://vihodjango.pixelstrap.com/"
                                    target="_blank"
                                    ><img
                                        class="img-fluid"
                                        src="../assets/images/landing/icon/django/django.png"
                                        alt=""
                                    />Django</a
                                ><a
                                    class="btn-landing btn-lg btn-danger ms-2"
                                    href="https://angular.pixelstrap.com/viho/dashboard/default"
                                    target="_blank"
                                    ><img
                                        class="img-fluid"
                                        src="../assets/images/landing/icon/angular/angular.png"
                                        alt=""
                                    />Angular</a
                                ><a
                                    class="btn-landing btn-lg btn-secondary ms-2"
                                    href="https://vue.pixelstrap.com/viho"
                                    target="_blank"
                                    ><img
                                        class="img-fluid"
                                        src="../assets/images/landing/icon/vue/vue.png"
                                        alt=""
                                    />Vue</a
                                >
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="position-block">
            <div class="circle1 opicity3" />
            <div class="star"><i class="fa fa-asterisk" /></div>
            <div class="star star1">
                <i class="fa fa-asterisk" />
            </div>
            <div class="star star2 opicity3">
                <i class="fa fa-asterisk" />
            </div>
            <div class="star star3"><i class="fa fa-times" /></div>
            <div class="star star4 opicity3">
                <i class="fa fa-times" />
            </div>
            <div class="star star5 opicity3">
                <i class="fa fa-times" />
            </div>
            <ul class="animat-block">
                <li>
                    <img
                        class="img-fluid img-parten top-parten"
                        src="../assets/images/landing/landing-home/home-position/img-parten.png"
                        alt=""
                    />
                    <div>
                        <img
                            class="img-fluid img1 v-align-t m-t-30"
                            src="../assets/images/landing/landing-home/home-position/img-1.jpg"
                            alt=""
                        /><img
                            class="img-fluid img2 v-align-t"
                            src="../assets/images/landing/landing-home/home-position/img-2.jpg"
                            alt=""
                        /><img
                            class="img-fluid img3 v-align-b"
                            src="../assets/images/landing/landing-home/home-position/img-3.jpg"
                            alt=""
                        /><img
                            class="img-fluid img4 v-align-b"
                            src="../assets/images/landing/landing-home/home-position/img-4.jpg"
                            alt=""
                        />
                    </div>
                </li>
                <li>
                    <div>
                        <img
                            class="img-fluid img5"
                            src="../assets/images/landing/landing-home/home-position/img-5.png"
                            alt=""
                        /><img
                            class="img-fluid img6 v-align-c"
                            src="../assets/images/landing/landing-home/home-position/img-6.jpg"
                            alt=""
                        />
                    </div>
                </li>
                <li>
                    <img
                        class="img-fluid img-parten bottom-parten"
                        src="../assets/images/landing/landing-home/home-position/img-parten.png"
                        alt=""
                    />
                    <div>
                        <img
                            class="img-fluid img7 v-align-t"
                            src="../assets/images/landing/landing-home/home-position/img-7.jpg"
                            alt=""
                        /><img
                            class="img-fluid img8 v-align-t"
                            src="../assets/images/landing/landing-home/home-position/img-8.jpg"
                            alt=""
                        /><img
                            class="img-fluid img9"
                            src="../assets/images/landing/landing-home/home-position/img-9.jpg"
                            alt=""
                        />
                    </div>
                </li>
            </ul>
        </div> -->
    </section>
    <!--home section end-->
    <!--demo section start-->
    <section class="demo-section section-py-space" id="demo">
        <!-- <div class="title">
            <h2>Creative Layouts</h2>
        </div>
        <div class="custom-container">
            <div class="row demo-block demo-imgs">
                <div class="col-lg-4 col-sm-6">
                    <div class="demo-box">
                        <div class="img-wrraper">
                            <img
                                class="img-fluid"
                                src="../assets/images/landing/demo/1.jpg"
                                alt=""
                            />
                            <div class="overlay">
                                <ul class="demo-link hover-link">
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="index.html"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/html/html.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="https://webiots.co.in/viho/dashboard/default?layout=default-sidebar"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/react/reactstrap.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="https://laravel.pixelstrap.com/viho/default-layout/"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/laravel/laravel.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="https://vihodjango.pixelstrap.com/default/?layout_type=defaul-layout"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/django/django.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="https://angular.pixelstrap.com/viho/dashboard/default?layout=false"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/angular/angular.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="default-demo"
                                            href="https://vue.pixelstrap.com/viho/?layout=Defaul"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/vue/vue.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="demo-detail">
                            <div class="demo-title">
                                <h3>Default Layout</h3>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4 col-sm-6">
                    <div class="demo-box">
                        <div class="img-wrraper">
                            <img
                                class="img-fluid"
                                src="../assets/images/landing/demo/2.jpg"
                                alt=""
                            />
                            <div class="overlay">
                                <ul class="demo-link">
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="dashboard-02.html"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/html/html.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="https://webiots.co.in/viho/dashboard/default?layout=compact-sidebar"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/react/reactstrap.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="https://laravel.pixelstrap.com/viho/compact-layout/"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/laravel/laravel.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="https://vihodjango.pixelstrap.com/ecommerce/?layout_type=compact-layout"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/django/django.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="https://angular.pixelstrap.com/viho/dashboard/default?layout=compact-layout"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/angular/angular.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="compact-demo"
                                            href="https://vue.pixelstrap.com/viho/?layout=Compact"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/vue/vue.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="demo-detail">
                            <div class="demo-title">
                                <h3>Compact Layout</h3>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4 col-sm-6 offset-sm-3 offset-lg-0">
                    <div class="demo-box">
                        <div class="img-wrraper">
                            <img
                                class="img-fluid"
                                src="../assets/images/landing/demo/3.jpg"
                                alt=""
                            />
                            <div class="overlay">
                                <ul class="demo-link">
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="general-widget.html"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/html/html.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="https://webiots.co.in/viho/dashboard/default?layout=modern-sidebar"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/react/reactstrap.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="https://laravel.pixelstrap.com/viho/modern-layout/"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/laravel/laravel.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="https://vihodjango.pixelstrap.com/general/?layout_type=modern-layout"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/django/django.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="https://angular.pixelstrap.com/viho/dashboard/default?layout=modern-layout"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/angular/angular.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                    <li>
                                        <a
                                            id="modern-demo"
                                            href="https://vue.pixelstrap.com/viho/?layout=Modern"
                                            target="_blank"
                                            ><img
                                                src="../assets/images/landing/icon/vue/vue.png"
                                                alt=""
                                            /></a
                                        >
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div class="demo-detail">
                            <div class="demo-title">
                                <h3>Modern layout</h3>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div> -->
    </section>
    <!--demo section end-->
</SubLayout>
