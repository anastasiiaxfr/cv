+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/hugo-breadcrumb-partial.jpg"
title = "Hugo Breadcrumbs"
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
[https://gohugo.io/content-management/sections/#example-breadcrumb-navigation](https://gohugo.io/content-management/sections/#example-breadcrumb-navigation "https://gohugo.io/content-management/sections/#example-breadcrumb-navigation")

[https://hugocodex.org/add-ons/breadcrumbs/](https://hugocodex.org/add-ons/breadcrumbs/ "https://hugocodex.org/add-ons/breadcrumbs/")  
[https://developers.google.com/search/docs/advanced/structured-data/breadcrumb?hl=ru](https://developers.google.com/search/docs/advanced/structured-data/breadcrumb?hl=ru "https://developers.google.com/search/docs/advanced/structured-data/breadcrumb?hl=ru")  
[https://schema.org/BreadcrumbList](https://schema.org/BreadcrumbList "https://schema.org/BreadcrumbList")

**My custom template:**

    <!-- BEGIN breadcrumbs -->
    <article class="breadcrumb__container">
    	<div class="row">
    		<div class="page-container">
    
    			<nav aria-label="breadcrumb">
    				<ol class="breadcrumb-wrap" itemscope itemtype="http://schema.org/BreadcrumbList">
    				
    				<li class="breadcrumb__item" itemprop="itemListElement" itemscope
    					itemtype="http://schema.org/ListItem">
    			
    					<a href="{{  .Site.BaseURL  }}" itemprop="item">
    						<span itemprop="name"> Home </span>
    						<meta itemprop="position" content="1" />
    					</a>
    				</li>
    			
    			{{ $findUrl := slice }}
    			{{ range $index, $el := (split .URL "/") }}
    			{{ if gt (len . ) 0 }}
    			{{ $findUrl = uniq ($findUrl | append .)  }}
    			{{ end }}
    			{{ end }}
    			{{ $url := "/" }}
    			
    			{{ range $index, $el := $findUrl }}
    			<li class="breadcrumb__item" itemprop="itemListElement" itemscope
    			itemtype="http://schema.org/ListItem">
    			{{ $url = "/" | add . | add $url  }}
    			
    			<a href="{{ $url }}"  itemprop="item">
    					<span itemprop="name"> {{ . }} </span>
    					{{ $index = $index | add 1 |  }}
    					<meta itemprop="position" content="{{ $index }}" />
    				</a>
    			</li>
    			{{ end }}
    			</nav>
    
    		</div>
    	</div>
    </article>
    <!-- END breadcrumbs -->