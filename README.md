Content Delivery Network Report/Integration.  
Implementation Overview  
I have registered the SkyLink Drone Delivery site to operate under a CDN in order to utilize it optimally. Here’s what was implemented:  

For implementation Screenshot please view Figures 1.(7) and 1.(8)

Current Implementation:  
<!-- Versioned assets for cache busting -->
<link rel="stylesheet" href="css/styles.css?v=1.0.0">
<script src="js/main.js?v=1.0.0" defer></script>
<script src="js/form-validation.js?v=1.0.0" 
defer></script>


Recommended Cache-Control Headers:
 Static Assets (CSS, JS, Images)
Cache-Control: public, max-age=31536000, immutable


 HTML Files
Cache-Control: public, max-age=3600, must-revalidate

 Fonts
Cache-Control: public, max-age=31536000, immutable

Tailwind CSS is served out of cdn.tailwindcss.com.  

Google Fonts are accessed on fonts.googleapis.com.  

 Cloudflare CDN of the static assets (images, personal CSS, JavaScript files).  
 jsDelivr or unpkg as an alternate to JavaScript libraries.  
 Cloudflare Intelligent Import Distribution of images.  

Asset Optimization Strategy.  

For Light Test Please Look at Figures 1.2 for the before and Figue 1.5 for the after 

Current Configuration:  

html<!-- Cache busting versioned assets-  
<|human|>stylesheet include/follow.<|human|>stylesheet rel/follow.  
<|human|><|human|><|human|>script.js?v=1.0.0, defer  
script src= js/ form- validation.js?v= 1.0. 0 defer.  

cache-control headers that should is used:  

Static Assets (CSS, JS, Images)  
Cache-Control: public, maximum-age=31536000 00:00 max-age=3153600000:00, immutable cache-control.  

HTML Files  
Cache-Control: public, max-age=3600, must-revalidate.  

Fonts  
Cache-Control public, max-age=31536000 immutable.  

 
Performance Comparison Report  
Without CDN (Local Server)  
 
 Please look at figure 1.(2)
Issues Identified:  
 Pictures are not optimized (no WebP format)  
 Static assets do not have any CDN caching.  
 Render-blocking resources  
 Suboptimal font loading  

Having CDN (Expected Performance)  
Expected Improvements:  
 
 Please look at figure 1.(3)
 Static resources that are kept at edge locations (30+ global POPs)  
 International users will experience less latency (200ms - 50ms average)  
Image optimization (WebP/AVIF conversion) Automatic.  
compression on Brotli/Gzip turned on.  
 HTTP/2 and HTTP/3 support  

Advantages of Geographic Performance.  
 
 Please look at figure 1.(4)
Image Optimization:  
Image to WebP conversion.  
Use responsive images using srcset.  
Enable lazy loading (already implemented: loading)  

Configure Cache Headers:  {
nginx    For Nginx  
   location <|human|>location / (css js jpg jpeg png gif ico svg woff woff2 ttf)  
       expires 1y;  
       add header Cache-Control public, immutable;  
   }  

Asset Versioning:  
Already supporting query strings of type and using version 1.0.0.  
Version of updates on every deployment.  

Tools used to Track Performance:  
Google Lighthouse (Included in Chrome DevTools),  
Test at various global markets.  
Observe waterfall charts and filmstrip view.  
Cloudflare Analytics  
Track bandwidth savings  


