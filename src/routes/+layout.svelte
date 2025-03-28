<script>
    let { children } = $props();
    import "../app.css";
    import { dev } from '$app/environment';
    import { injectAnalytics  } from '@vercel/analytics/sveltekit';

    injectAnalytics({ mode: dev ? 'development' : 'production'});

    import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';

    injectSpeedInsights();
</script>

{@render children()}