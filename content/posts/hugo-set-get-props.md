+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/breadcrumbs-seo-710x400.png"
title = "Hugo Set/Get/Props"
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

[https://regisphilibert.com/blog/2018/02/hugo-the-scope-the-context-and-the-dot/](https://regisphilibert.com/blog/2018/02/hugo-the-scope-the-context-and-the-dot/ "https://regisphilibert.com/blog/2018/02/hugo-the-scope-the-context-and-the-dot/")

  
Parent: {{ .Scratch.Set "prop" val }}

Child: {{ $var := .Scratch.Get "prop" }}

![](/images/4a2498d28e-1.jpg)

    {{ $display_posts := ((.Site.GetPage "section" "/game").Pages).ByDate.Reverse }}
    {{ $paginator := .Paginate $display_posts }}
    {{ range $post := $paginator.Pages }}
    {{ partial "_game-card-main.html" (dict "context" . "post" $post ) }}
    {{ end }}

**My custom template:**

Parent component

     {{ .Scratch.Set "img" .Site.Params.logo_white }}
     {{ .Scratch.Set "logo_w" 170 }}
     {{- partial "_logo.html" . -}}
    

Child component

    <!--Logo Box-->
    {{ $img := .Scratch.Get "img" }}
    {{ $logo_w := .Scratch.Get "logo_w" }}
    
    
    <div class="logo">
       <a href="{{ .Site.BaseURL | relLangURL }}">
          <img src="{{ $img | relURL }}" width="{{ $logo_w }}" alt="{{ .Title }}">
       </a>
    </div>
    