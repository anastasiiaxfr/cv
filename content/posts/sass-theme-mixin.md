+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/sass.jpg"
title = "Sass Theme Mixin"
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
    =theme($theme)
    	@if $theme == dark
    		background-color: $black
    		color: $white
    
    	@if $theme == white
    		background-color: $white
    		color: $gray
    
    	@if $theme == main
    		background-color: $main
    		color: $gray
    
    	@if $theme == light
    		background-color: rgba($yellow_light, 0.5)
    		color: $black
    
    	@if $theme == gray
    		border-radius: $brs2 
    		background-color: $gray_light
    		color: $gray
    
    +theme(dark)
    