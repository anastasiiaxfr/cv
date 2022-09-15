+++
date = 2021-12-19T22:00:00Z
feature_image = "/images/sass.webp"
title = "Sass Fonts mixin"
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
    $fontSrc: '../fonts'
    
    $fontFamily: 'Montserrat'
    
    
    $fntName: (Montserrat-Black, 900), (Montserrat-ExtraBold, 800), (Montserrat-Bold, 700), (Montserrat-SemiBold, 600), (Montserrat-Medium, 500), (Montserrat-Regular, 400), (Montserrat-Light, 300)
    
    
    =font($fntName, $fntSrc, $fontFamily)	
    	@each $fnt, $fntw in $fntName
    		@font-face 
    			$fntFldr: $fontFamily
    			font-family: $fontFamily
    			font-style: normal
    			font-weight: #{$fntw}
    			font-display: swap
    			src: local($fontFamily), local($fontFamily), url($fontSrc + '/' + $fntFldr + '/' +'#{$fnt}.woff') format('woff'), url($fontSrc + '/' + $fntFldr + '/' +'#{$fnt}.woff2') format('woff2'), url($fontSrc + '/' + $fntFldr + '/' +'#{$fnt}.ttf') format('ttf')
    
    
    
    
    
    +font($fntName, $fontSrc, $fontFamily)
    
    	

    =ft($fz, $lh: 16, $fw: 400, $ff: $ffText)
    	$lh: $lh/$fz
    	$fz: $fz/16 + rem
    	$ff: $ff, $ffBack
    	font: $fw $fz/$lh $ff 
        
    +ft(16, 16, 600, $ffHeading)
        