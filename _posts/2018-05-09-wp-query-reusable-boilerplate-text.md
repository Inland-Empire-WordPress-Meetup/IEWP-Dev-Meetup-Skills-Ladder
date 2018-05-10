---
ID: 4545
post_title: 'WP Query: Reusable Boilerplate Text'
author: Joseph Dickson
post_excerpt: ""
layout: post
permalink: >
  https://inlandempirewp.com/wp-query-reusable-boilerplate-text/
published: true
post_date: 2018-05-09 21:13:31
---
<strong>WP Query</strong> is the perfect solution for creating <strong>reusable boilerplate text</strong> for your site without the need of a separate plugin. To oversimplify <a href="http://codex.wordpress.org/Class_Reference/WP_Query" target="_blank" rel="noopener">WP Query</a> allows you to customize your theme using the power of the <a href="https://codex.wordpress.org/The_Loop" target="_blank" rel="noopener">WordPress Loop</a> without editing it directly. WP Query is a Class Reference that provides access to retrieve information from the database.
<h2>The WP Query code sample</h2>
<pre class="EnlighterJSRAW" data-enlighter-language="null">// The Query
$the_query = new WP_Query( array( 'name' =&gt; 'boilerplate' ) );

// The Loop
if ( $the_query-&gt;have_posts() ) {

 while ( $the_query-&gt;have_posts() ) {

  $the_query-&gt;the_post();

  echo '<div class="boilerplate">';

  echo '<strong>' . get_the_title() . '</strong>';

  the_content(); echo '</div>';

 }

/* Restore original Post Data */
 wp_reset_postdata();

 } else { 

// no posts found

}

</pre>

<strong>Setting the Variable</strong>

To begin lets set $the_query variable to look for a post with the slug name "boilerplate" this will require you to create a new post with that precise slug name. Feel free to change it as you see fit.

<strong>Creating the Loop
</strong>

This second portion of the code checks if your variable has retrieved a post. If a post is found the while portion continues where HTML is echoed around the templates tags <a href="https://developer.wordpress.org/reference/functions/get_the_title/" target="_blank" rel="noopener">get_the_title()</a> and <a href="https://developer.wordpress.org/reference/functions/the_content/" target="_blank" rel="noopener">the_content()</a> which retrieve the title and content from your post respectively. Lastly <a href="https://codex.wordpress.org/Function_Reference/wp_reset_postdata" target="_blank" rel="noopener">wp_reset_postdata()</a> completes the process and closes the loop so it doesn't interfere with anything else that may be running on the page.

<strong>Final Step</strong>

add the code to template files such as single.php so that the boilerplate post text is automatically added to your posts at whatever place you choose to add the code.

[caption id="attachment_4548" align="aligncenter" width="858"]<a href="https://inlandempirewp.com/wp-content/uploads/2018/05/Screenshot-from-2018-05-09-20-39-45.png"><img class="size-full wp-image-4548" src="https://inlandempirewp.com/wp-content/uploads/2018/05/Screenshot-from-2018-05-09-20-39-45.png" alt="WP Query Boilerplate example" width="858" height="533" /></a> An example of the <strong>boilerplate post</strong> in action within a child theme based on Twenty Seventeen.[/caption]