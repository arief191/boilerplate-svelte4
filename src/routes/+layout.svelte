<script>
    import "../app.css";
    import { afterNavigate } from '$app/navigation';

    afterNavigate(({ to }) => {
        window.parent?.postMessage(
             { type: 'iframe:navigated', path: to.url.pathname, full: to.url.href },
            '*'
        );
    });
</script>
  
<slot />