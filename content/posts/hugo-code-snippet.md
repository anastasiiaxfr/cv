+++
date = 2021-12-19T22:00:00Z
draft = true
feature_image = "/images/1_i-0frqrx0ckyfsap_k6n_a.jpeg"
title = "Hugo Code Snippet"
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
**Range / Loop**

**If / Else**

**Random**

**URL**

Examples:

List.html (Parent Page)

    {{ define "main" }}
    {{ $data := index .Site.Data .Site.Language.Lang }}
    
    {{ if .Params.domains.enable }}
    	{{ with .Params.domains }}
    		{{ partial "_domains-single.html" . }}
        {{ end }}
    {{ end }} 	
    
    {{ end }}

    
    <ul class="checks list-location">
      {{ $count := slice }}
      {{ range $i, $arr := .Data.Pages }} 
      {{ $count = $count | append $i }}
      {{ end }}
    
      {{ if gt (len $count) 4 }}
          
      {{ range $i, $arr := .Data.Pages }} 
      {{ if not .Params.draft }}
    
      {{ if .Params.country_title}}
      <li>
        <a href="{{ .Permalink | relURL }}">
          {{ .Params.country_title | truncate 50 }}
        </a> 
      </li>
      {{ end }} 
      {{ end }}
      {{ end }}
    
      {{ else }}
     
      {{ if .Params.geo }}
        {{ range first 50 .Params.geo.list }}
        <li> 
            <!-- <a href="{{ .url }}{{ .code }}"> -->
               {{ .item | truncate 50 }} 
            <!-- </a> -->
        </li>
        {{ end }} 
    
      {{ end }}
    
      {{ end }}
    </ul>