---
layout: page
title: App QR
include_in_header: false
include_in_footer: false
---

<script>
    // Helper to get current URL's query string (preserves utm_* if present)
    const query = window.location.search;

    // Your App Store link (replace ID)
    const appStoreBase = 'https://apps.apple.com/app/id{{ site.ios_app_id }}';

    const forwardParams = query; // or filter if needed

    const target = appStoreBase + forwardParams;

    setTimeout(() => {
        window.location.href = target;
    }, 300);
</script>

<p style="text-align: center;">
    Redirecting to the App Store.
    <br>
    If you’re not redirected automatically, 
    <a id="fallback" href="https://apps.apple.com/app/id{{ site.ios_app_id }}">
        click here
    </a>.
</p>
