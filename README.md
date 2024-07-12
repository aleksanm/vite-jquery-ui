
Jaunais Laravel projekts ar Vite, kurā iekļauts jQuery un jQuery-ui, bootstrap
Kā šitais top.
1. Varam git clone šo repozitoriju un tad iet uz so projektu
```shell
cd vite-jquery-ui
```
2. Vai arī izveidojam jaunu Laravel projektu
```shel
laravel new vite-jquery-ui // te uzinstalējam pliku projektu
```
```shell
cd vite-jquery-ui
```
```shell
npm install jquery // instalējam jquery
```
```shell
npm i --save bootstrap @popperjs/core // instalējam bootstrap
```
```shell
npm i --save-dev sass // instalējam bootstrap dependencies
```
Apciemojam jquery-ui saiti: https://jqueryui.com/download/ un lejupielādējam vajadzīgo versiju
Izvelkam failus un ieliekam resources/js un resources/css mapēs
Faili, ko izvelkam ir jquery-ui.min.js un jquery-ui.css, jquery-ui.theme.css, 
attiecīgi js iekš resources/js un css iekš resources/css
Priekš šādām, tādām ikonām nepieciešams arī images mape, tāpēc ieliekam arī to resources/css/images mapē,
labāk uztaisam jaunu mapi resources/css/jquery-ui un ieliekam tur iepriekšējās css failus un images mapi

tad rediģējam vite.config.js failu, lai importētu jquery un jquery-ui, bootstrap
tad rediģējam app.js, lai importētu jquery un jquery-ui, bootstrap
Attiecīgi ir izveidots jauns jquery.js fails, kurā importēts jquery,
lai varētu izmantot visās lapās un jquery-ui neteiktu, ka nav jquery // !!! svarīgi
Attiecigi ir izveidots jauns jquery-ui.css fails, kurā importēts jquery-ui,
šie visi ir norādīti vite.config.js failā, lai varētu izmantot visās lapās

Tad index.blade.php vai kādā citā failā ieliekam šādu kodu:
```html
<!-- Scripts -->
        @vite(['resources/css/app.css', 'resources/sass/bootstrap.scss', 'resources/css/jquery-ui.css', 'resources/js/app.js'])
```
```shell
npm run build
```
Tur vite kaut ko lamājas par nested scss, bet tas bootstrapam, viņi paši kaut kad to novērsīs.

Finish: atveram lapu un pārbaudam, ka viss strādā kā vajag

