```javascript
<a href="/analytics/funders.html">Funders</a>
<a href="/analytics/scientists.html">Scientists</a>

<script type="text/javascript">
    require(['app/js/radar'], function (App) {
        $('a').on('click', function (e) {
            e.preventDefault();
            var loadIntoAnalyticalView = App.get('loadAnalyticalView');
            var pushState = App.get('pushState');

            // Load source from href
            loadIntoAnalyticalView($(this).attr('href'));

            // Push the state change
            pushState({'analytics': true}, '', $(this).attr('href').replace('.html', ''));
        });

        require(['app/js/radar'], function (App) {
            // Request path update on startup
            App.updatePath('analytics', '{{ request.path }}'.replace('.html', ''));
        });
    });
</script>
```