+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/dy2nhxuvyaazvy0.jpg"
title = "Sass Position Mixin"

+++
    // +position(absolute, (t, 0), (r, 0))
    =position($ps, $val)
    	@each $x in $ps
    		@if $x == t
    			top: $val
    
    		@if $x == b
    			bottom: $val
    
    		@if $x == l
    			left: $val
    
    		@if $x == r
    			right: $val
    
    =ps($params...)
    	position: nth($params, 1)
    	@each $par, $val in $params
    		@if $par != null and $val != null
    			+position($par, $val)