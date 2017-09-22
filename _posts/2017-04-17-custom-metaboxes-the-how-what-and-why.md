---
ID: 4439
post_title: 'Custom Metaboxes &#8212; The How, What, and Why'
author: Nate Conley
post_excerpt: ""
layout: post
permalink: >
  https://inlandempirewp.com/custom-metaboxes-the-how-what-and-why/
published: true
post_date: 2017-04-17 13:44:37
---
Custom metaboxes are an incredibly powerful and useful part of the WordPress ecosystem. What are they and how can they be used? Let's dive in!
<h2>The What &amp; WHY</h2>
Custom metaboxes are stand alone boxes that can be added to the WordPress editor. They are a user interface for storing information attached to a post, called the postmeta. They are highly customizable and can be fairly easy to use. While you can use the built-in Custom Fields box in WordPress, and it can be advantageous at times, using your own custom metaboxes is often a better solution. They can be easier and more intuitive for anyone using the editor, and they are much more customizable than the Custom Fields box.
<h2>The How (Three Ways)</h2>
<h3>Easiest - Advanced Custom Fields</h3>
Advanced Custom Fields is a really handy plugin you can use to add custom metaboxes to your site. It is incredibly powerful, despite being fairly easy to start using.
<h6>PROs</h6>
<ul>
 	<li>Easy to Use and Set Up</li>
 	<li>Great Documentation</li>
 	<li>They offer many paid and free add-ons</li>
</ul>
<h6>CONS</h6>
<ul>
 	<li>You must purchase a license to unlock many of the advanced features</li>
 	<li>The postmeta is stored in two rows in the database (an important consideration on large sites)</li>
</ul>
<h6>RESOURCES</h6>
<a href="https://www.advancedcustomfields.com/">https://www.advancedcustomfields.com/</a>
<h3>A Little More Technical - CMB2</h3>
CMB2 is a really useful tool that makes coding custom metaboxes a little less painful. Maintained by WebDevStudios, CMB2 lets developers build metaboxes without all of the code and settings required by a pure solution.
<h6>PROS</h6>
<ul>
 	<li>Available in plugin form or as a bootstrap</li>
 	<li>Great documentation and code examples on their GitHub repository</li>
</ul>
<h6>CONS</h6>
<ul>
 	<li>You have to write code</li>
 	<li>It is a toolkit, not a complete solution with a GUI</li>
</ul>
<h6>Resources</h6>
<a href="https://github.com/CMB2/CMB2">https://github.com/CMB2/CMB2</a>

<a href="https://cmb2.io/">https://cmb2.io/</a>

<a href="https://github.com/CMB2/CMB2-Snippet-Library">https://github.com/CMB2/CMB2-Snippet-Library</a>
<h3>Down &amp; Dirty With Code - WordPress API</h3>
Your first experience with writing your own custom metaboxes is likely to be filled with a lot of banging your head against a hard surface. But, like so many other WordPress APIs, after the first time you build it, it keeps getting significantly easier. Using built-in features is arguably the best route to go if you plan on distributing your WordPress project to others, as it is lightweight and writing the "WordPress" way usually means you are better setup for future-proofing.
<h6>PROS</h6>
<ul>
 	<li>You have complete control</li>
 	<li>The best solution for distributing your own plugins or themes</li>
</ul>
<h6>CONS</h6>
<ul>
 	<li>This is the most amount of work out of the three</li>
</ul>
<h6>RESOURCES</h6>
<a href="https://developer.wordpress.org/plugins/metadata/custom-meta-boxes/">https://developer.wordpress.org/plugins/metadata/custom-meta-boxes/</a>