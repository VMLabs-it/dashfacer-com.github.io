---
layout: page
title: App QR
include_in_header: false
include_in_footer: false
---

<script>
    const query = window.location.search;
    const ua = navigator.userAgent || navigator.vendor || window.opera;

    const isAndroid = /android/i.test(ua);

    const appStoreUrl = 'https://apps.apple.com/app/id{{ site.ios_app_id }}' + query;
    const playStoreBase = '{{ site.playstore_link }}';
    const playStoreUrl = query ? playStoreBase + (playStoreBase.includes('?') ? '&' : '?') + query.slice(1) : playStoreBase;

    const target = isAndroid ? playStoreUrl : appStoreUrl;

    setTimeout(() => {
        window.location.href = target;
    }, 300);
</script>

<p style="text-align: center;">
    Redirecting to the app store for your device.
    <br>
    If you are not redirected automatically, download on
    <a href="https://apps.apple.com/app/id{{ site.ios_app_id }}">App Store</a>
    or
    <a href="{{ site.playstore_link }}">Google Play</a>.
</p>
