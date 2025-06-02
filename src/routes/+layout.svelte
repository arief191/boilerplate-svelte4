<script>
    import "../app.css";
    import { afterNavigate } from '$app/navigation';

    afterNavigate(({ to }) => {
        window.parent.postMessage({ pathname: to.url.pathname }, '*');
    });
</script>
  
<slot />