---
ID: 4400
post_title: 'You Can Make A Plugin &#038; A Shortcode Too'
author: Verious
post_excerpt: ""
layout: post
permalink: >
  https://inlandempirewp.com/can-make-plugin-shortcode/
published: true
post_date: 2016-09-06 19:10:04
---
&nbsp;

<img class="alignnone size-full wp-image-4415" src="https://inlandempirewp.com/wp-content/uploads/2016/09/pluginandshortcodetoo-1.jpg" alt="you can create a plugin and a shortcode too." width="960" height="503" />

Much of this code and these examples can be found in the <a href="https://developer.wordpress.org/plugins/" target="_blank">Plugin Developer's Handbook area of the WordPress Codex</a>.  This post is a guide for our in-person meetup but can be used to dig deeper later.
<h3>WordPress Plugins</h3>
Writing a plugin is one of those abilities that will give you superpowers in WordPress.   Of the 46,000 + plugins that are currently on the WordPress Directory you are bound to find a plugin to fit your need.  The great thing about WordPress Is that it is infinitely extendible and even if you do not find a plugin to fit your need you can always create your own plugin.

If you are setting out on the road to create your own plugin, what are the absolute basics that you will need?
<h3>A Basic Plugin</h3>
A WordPress Plugin is made out of PHP so for the basics of a plugin all you really need is a PHP file.   You can use whatever name you like but you will need to add  some very specific code to this PHP file.

[php]

/*
Plugin Name: My Plugin
*/

[/php]

Yes, this is all you actually need in a PHP file to begin your first plugin.  This actually does not do anything.  For your plugin to actually have functionality you will need to add functions to the plugin.  Before we  actually place functions in your code you will need to know where you will need to place the plugin in your file directory.

All of your plugins will be located in the WordPress plugin directory.  The plugin directory is located here (In relation to your root directory):
<ul>
 	<li>/root directory
<ul>
 	<li>/wp-content
<ul>
 	<li>/themes</li>
 	<li>/plugins
<ul>
 	<li>my-plugin.php</li>
</ul>
</li>
</ul>
</li>
 	<li>/wp-admin</li>
 	<li>/wp-includes</li>
</ul>
</li>
</ul>
<h3>Plugins Functions</h3>
Functions in your plugin can range from the simple to incredibly complex.  This Post will not go over how to write PHP functions but if you are familiar with PHP then you can definitely write your own.  The best way for you to proceed in developing a WordPress Plugin that will play nicely with all of the other 48 K plus plugins in the WordPress directory is for you to follow the WordPress coding guidelines and use all of the current WordPress API"s that are available to you.
<h3>WordPress Coding Standards</h3>
The WordPress Coding Standards are a set of rules &amp; best practices that are put out by the community that ensure consistent quality of code regardless of who the code is written by.  You can find the complete documentation and begin to familiarize yourself with all of the<a href="https://codex.wordpress.org/WordPress_Coding_Standards" target="_blank"> WordPress Coding Standards for HTML, CSS, PHP &amp; JS in the WordPress Codex</a>.
<h3>WordPress API's</h3>
If you are actually going to dig into the WordPress API's further than you will discover true power for controlling the technology behind WordPress.  In order for you to find out more about the WordPress API's you can go to the WordPress Codex and read about them.   <a href="https://codex.wordpress.org/WordPress_APIs" target="_blank">WordPress API Codex</a>
<h3>Writing A Simple ShortCode</h3>
From the Plugin Developers Handbook:
<blockquote>Shortcodes are registered with WordPress by declaring a shortcode and assigning a callback. At it’s simplest, here’s a Hello Dolly example:

[php]
function hello_dolly_shortcode() {
return "Hello Dolly";
}
add_shortcode( 'hello-dolly', 'hello_dolly_shortcode' );
[/php]

[hello-dolly] is your new shortcode, and use of the shortcode will trigger the hello_dolly_shortcode() callback function.</blockquote>
&nbsp;

&nbsp;

&nbsp;