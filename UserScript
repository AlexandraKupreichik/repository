// ==UserScript==
// @name         Автоматический переход между страницами
// @namespace    ваше_пространство_имен
// @version      1.0
// @description  Автоматический переход между страницами и выполнение кода после каждого перехода.
// @match        http://localhost:63342/StrayKids/index.html
// @grant        none
// ==/UserScript==

(function() {
    var pages = ["http://localhost:63342/StrayKids/pages/discography.html",
        "http://localhost:63342/StrayKids/index.html",
        "http://localhost:63342/StrayKids/pages/members.html",
        "http://localhost:63342/StrayKids/pages/tour.html",
        "http://localhost:63342/StrayKids/pages/gallery.html"
    ];

    var currentIndex = 0;

    function visitNextPage() {
        if (currentIndex < pages.length) {
            var nextPageIndex = Math.floor(Math.random() * pages.length);
            while (nextPageIndex === currentIndex) {
                nextPageIndex = Math.floor(Math.random() * pages.length);
            }
            currentIndex = nextPageIndex;
            window.location.href = pages[currentIndex];
        } else {
            console.log("Все страницы просмотрены");
            clearInterval(mouseMoveInterval);
        }
    }

    function simulateMouseMove() {
        var x = Math.floor(Math.random() * window.innerWidth);
        var y = Math.floor(Math.random() * window.innerHeight);
        window.scrollTo(x, y);
    }

    function simulateClick() {
        var elements = document.getElementsByTagName("a");
        var randomIndex = Math.floor(Math.random() * elements.length);
        var element = elements[randomIndex];

        var event = new MouseEvent("click", {
            bubbles: true,
            cancelable: true,
            view: window
        });

        element.dispatchEvent(event);
    }

    var mouseMoveInterval = setInterval(simulateMouseMove, 500);

    window.addEventListener("load", function() {
        simulateClick();
        console.log("Вы на странице: " + window.location.href);
    });

    setInterval(function() {
        visitNextPage();
    }, 10000);
})();
