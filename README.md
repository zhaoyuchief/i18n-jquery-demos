# i18n-jquery-demos

###引用jquery及i18next插件
* jquery.js
* i18next.min.js
* i18nextBrowserLanguageDetector.min.js
* jquery-i18next.min.js

###填写html标签属性

```html
<ul class="nav">
    <li><a href="#" data-i18n="nav.home"></a></li>
    <li><a href="#" data-i18n="nav.page1"></a></li>
    <li><a href="#" data-i18n="nav.page2"></a></li>
</ul>
```
###初始化i18next.init

```js
i18next.use(window.i18nextBrowserLanguageDetector)
        .init({
                load:'all',
                lng: 'en', // evtl. use language-detector https://github.com/i18next/i18next-browser-languageDetecto
                debug: true,
                resources: { // evtl. load via xhr https://github.com/i18next/i18next-xhr-backend
                    en: {
                        translation: {
                            input: {
                                placeholder: "a placeholder"
                            },
                            nav: {
                                home: 'Home',
                                page1: 'Page One',
                                page2: 'Page Two'
                            }
                        }
                    },
                    zh: {
                        translation: {
                            input: {
                                placeholder: "a placeholder"
                            },
                            nav: {
                                home: '首页',
                                page1: '页面1',
                                page2: '页面2'
                            }
                        }
                    }
                }
            }, function (err, t) {

            jqueryI18next.init(i18next, $);

            console.warn(i18next.t('input.placeholder'));
            console.warn(i18next.t('nav.home'));
            console.warn(i18next);

            $('body').localize();
    });
```    
###点击按钮更改语言

```html
     i18next.changeLanguage(lan, (err, t) => {
            // resources have been loaded
            $('body').localize();
        });
```