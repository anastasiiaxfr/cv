+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/1_i-0frqrx0ckyfsap_k6n_a.jpeg"
title = "Hugo main Config"
tags = [
    "markdown",
    "css",
    "html",
    "gulp",
]
categories = [
    "markup",
    "gulp",
]
+++
    baseURL = "/"
    
    canonifyURLs = true
    relativeURLs = true
    
    defaultContentLanguage = "ua"
    disableLanguages = []
    languageCode = "ua"
    
    paginate = "6"
    summaryLength = "50"
    
    [outputs]
    home = ["HTML", "RSS", "JSON"]
    
    [sitemap]
    ChangeFreq = "daily"
    Priority = 0.6
    Weight = [["main", "1"], ["sub2", "0.8"], ["sub3", "0.6"]]
    enableRobotsTXT = true
    
    [taxonomies]
    author = "authors"
    category = "categories"
    tag = "tags"
    
    [Languages.ru]
    contentDir = "content/ru"
    home = "Главная"
    languageCode = "ru"
    languageName = "Ру"
    weight = 2
    
    [Languages.ua]
    contentDir = "content/ua"
    home = "Головна"
    languageCode = "ua"
    languageName = "Укр"
    weight = 1
    
    
    # CSS Plugins
    [[params.plugins.css]]
    link = "plugins/bootstrap/bootstrap.min.css"
    [[params.plugins.css]]
    
    # JS Plugins
    [[params.plugins.js]]
    link = "plugins/slick/slick.min.js"
    
    # main menu
    [[menu.main]]
    name = "page1"
    URL = "/"
    weight = 1
    
    [[menu.main]]
    identifier = "page2"
    name = "page2"
    URL = "/page2/"
    weight = 2