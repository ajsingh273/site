dynamic rendering API on a webpage
```
<div id="results_container">
</div>
</div>
<script>
    $(document).ready(function() {
        get_results();
    });

    function get_results() {
        $.getJSON('https://api.com/', function(d) {
            $("#results_container").empty();
            for (x in d.results) {

                var domain = d.results[x].trade_url.replace('https://www.url.gov/', '');

                row = '<div id="result_' + x + '"><a href="' + domain + '"><h1 class="result_title">' + d.results[x].title + '</h1></a></div>'
                if (x < d.results.length - 1) {

                }
                row = row + "</div>";
                $("#results_container").append(row);

            }

        });
    }
</script>
```