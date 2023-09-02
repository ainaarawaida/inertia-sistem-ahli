<script>
    import { onMount } from "svelte";

    export let message;

    onMount(async () => {
        let checkload = setInterval(async () => {
            if (window.jQuery && window.toastr) {
                await toastrinc(message);
                clearInterval(checkload);
            }
        }, 1000);
    });

    let toastrinc = (message) => {
        console.log("ddd", message);
        toastr.options = {
            closeButton: true,
            progressBar: true,
        };
        if (message) toastr.success(message);
    };
</script>

<!-- export function toastrinc(message) {


    toastr.options =
    {
        "closeButton": true,
        "progressBar": true
    }
    toastr.success("success");

    @if (Session:: has('message'))
    toastr.options =
    {
        "closeButton": true,
        "progressBar": true
    }
    toastr.success("{{ session('message') }}");
    @endif

    @if (Session:: has('error'))
    toastr.options =
    {
        "closeButton": true,
        "progressBar": true
    }
    toastr.error("{{ session('error') }}");
    @endif

    @if (Session:: has('info'))
    toastr.options =
    {
        "closeButton": true,
        "progressBar": true
    }
    toastr.info("{{ session('info') }}");
    @endif

    @if (Session:: has('warning'))
    toastr.options =
    {
        "closeButton": true,
        "progressBar": true
    }
    toastr.warning("{{ session('warning') }}");
    @endif

} -->
