<main>
    <svelte:component this={Route} {params} />
</main>

<script>
	import Navaid from 'navaid';
    import Header from './Header.svelte';
    import { onDestroy } from 'svelte';
    let Route, params, active;
    let uri = location.pathname;
    $: active = uri.split('/')[1] || 'home';
    function draw(m, obj) {
        params = obj || {};
        if (m.preload) {
            m.preload({ params }).then(() => {
                Route = m.default;
            });
        } else {
            Route = m.default;
        }
    }
    function track(obj) {
        uri = obj.state || obj.uri;
        if (window.ga) ga.send('pageview', { dp:uri });
    }
    addEventListener('replacestate', track);
    addEventListener('pushstate', track);
    addEventListener('popstate', track);
    const router = Navaid('/')
        .on('/', () => import('../routes/Home.svelte').then(draw))
        .on('/about', () => import('../routes/About.svelte').then(draw))
        .on('/blog', () => import('../routes/Blog.svelte').then(draw))
        .on('/blog/:title', obj => import('../routes/Article.svelte').then(m => draw(m, obj)))
        .listen();
    onDestroy(router.unlisten);
</script>


</script>
<div class="header-container">
    <button class="title-button">Kaelan Moffett-Steinke</button>
    <div class="menu-container">
        <button class="menu-buttons">Home</button>
        <button class="menu-buttons">Portfolio</button>
        <button class="menu-buttons">Contact</button>
    </div>
</div>

