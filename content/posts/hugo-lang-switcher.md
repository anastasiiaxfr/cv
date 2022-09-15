+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/language-picker.png"
title = "Hugo Lang Switcher"
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
**Docs:**  
[https://gohugo.io/content-management/multilingual/](https://gohugo.io/content-management/multilingual/ "https://gohugo.io/content-management/multilingual/")

       <!-- BEGIN lang-switcher -->
       {{ if .IsTranslated }}
       <li class="dropdown lang-switcher">
         {{ $siteLanguages := .Site.Languages}}
         {{ $pageLang := .Page.Lang}}
         <button class="" type="button" id="lang" data-toggle="lang" aria-haspopup="true"
           aria-expanded="false">
           {{ $pageLang }} <i class="fa fa-angle-down"></i>
         </button>
         <ul class="dropdown-menu" aria-labelledby="lang" id="select-language">
           {{ range .Page.AllTranslations }}
           {{ $translation := .}}
           {{ range $siteLanguages }}
           {{ if eq $translation.Lang .Lang }}
           {{ $selected := false }}
           {{ if eq $pageLang .Lang}}
           
           <li>
            <button class="" id="{{ $translation.Language }}" value="{{ $translation.RelPermalink }}"
            onClick="location = this.value;">{{ .LanguageName }}</button>
           </li>
         
           {{ else }}
           <li>
            <button class="" id="{{ $translation.Language }}" value="{{ $translation.RelPermalink }}"
            onClick="location = this.value;">{{ .LanguageName }}</button>
          </li>
    
           {{ end }}
           {{ end }}
           {{ end }}
           {{ end }}
         </ul>
        </li>
       {{ end }}
       <!-- END lang-switcher -->