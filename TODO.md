# To do - Things to add
* Bash: Learnings from 'https://github.com/JonasTaulienSolutions/bash-configuration/blob/master/configure-bash'
* `npm --prefix ./angular-app run start`
* CSS: Real viewport height on ios-safari 
    * in typescript

        ```typescript
        export class AppComponent implements OnInit {
            ngOnInit(): void {
                this.setRealViewPortHeightProperty();
                
                fromEvent(window, 'resize')
                    .pipe(
                        debounceTime(100)
                    )
                    .subscribe(() => this.setRealViewPortHeightProperty());
        
            }
        
            setRealViewPortHeightProperty() {
                const vh = window.innerHeight * 0.01;
                document.documentElement.style.setProperty('--real-vh', `${vh}px`);
            }
        }
        ```
    * then in css: `calc(var(--real-vh, 1vh) * 100)`)
* Angular ViewChild/ContentChild & ViewChildren/ContentChildren
* Angular: Place content children seperately using `<ng-template>` and a `TemplateMarkerDirective`
* Angular ChangeDetectorRef & ExpressionChangedAfterEvaluatedException
* Angular ControlValueAccessor
* Angular height-adjusting textarea
* Angular wrapping ControlValueAccessor
* Angular unit testing
* Angular module-setup
* Angular guards (with parameters)
* Angular reactive forms
* Css styling input=range
* JS: luxon
* JS: rxjs
* Angular @angular/cdk/overlay
* HTML: Responsive SVG using viewBox and preserveAspectRatio
* JWT in vertx and angular
* Angular: Carousel
* JS flatMap array
* Java Dockerfile
* Vertx: OpenAPI3RouterFactory
* Java - Google Maps
* Vertx Json: Java-times (JavaTimeModule()) and SerializationFeature.WRITE_DATES_AS_TIMESTAMPS
* Java: Password hashing with argon2
* Java: hikari data source for jooq
* jooq: insert
* jooq: fetch simple
* jooq: fetch 1 to n
* IntelliJ: Learnings from 'https://github.com/JonasTaulienSolutions/idea-plugin-context-free-grammar'
* css: flexbox
* css: BEM
* learnings from 'https://github.com/JonasTaulienSolutions/playground' (then delete)
* Learnings from articles from https://www.nickkolenda.com
* opening localhost web-application on ios-device (with squidman or via cable)