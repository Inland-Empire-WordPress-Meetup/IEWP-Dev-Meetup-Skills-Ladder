---
ID: 4490
post_title: Using Conditional Tags in WordPress
author: Joseph Dickson
post_excerpt: ""
layout: post
permalink: >
  https://inlandempirewp.com/using-conditional-tags-in-wordpress/
published: true
post_date: 2018-03-04 17:45:03
---
Conditional tags can be used to customize your WordPress website when <strong>TRUE</strong> or <strong>FALSE</strong> conditions are met.

This introductory example will show you how to display some of the post author's user information when on an individual post or the author's archive page.

[caption id="attachment_4493" align="aligncenter" width="1069"]<a href="https://inlandempirewp.com/?attachment_id=4493"><img class="wp-image-4493 size-full" src="https://inlandempirewp.com/wp-content/uploads/2018/03/author-php.jpg" alt="Sample conditional tag code" width="1069" height="396" /></a> This checks if the currently displayed page is a post or author archive then displays the user description and email.[/caption]
<pre class="EnlighterJSRAW" data-enlighter-language="php">&lt;?php
/*
 * Conditional Tags
 * When on an archive or post page display
 * user description and email address
 *
 */

if ( is_author() || is_single() ) {

        echo '&lt;p&gt;&lt;strong&gt;About the Author&lt;/strong&gt;&lt;br /&gt;' . get_the_author_meta( 'description' ) . '&lt;/p&gt;' ; 

        echo '&lt;p&gt;&lt;a href="mailto:' . get_the_author_meta( 'user_email' ) . '"&gt;' . get_the_author_meta( 'user_email' ) . '&lt;/a&gt;&lt;/p&gt;';

} else {
        /* 
         * Do nothing 
         * */
        
}
?&gt;</pre>
<h2>What this code does</h2>
When the displayed page is an <a href="https://codex.wordpress.org/Function_Reference/is_author" target="_blank" rel="noopener">author archive</a> or a <a href="https://developer.wordpress.org/reference/functions/is_single/" target="_blank" rel="noopener">single post</a> the conditions are met and return a value of TRUE. This displays the text <strong>About the Author</strong> in bold followed by that <strong>author's biographical information</strong> and <strong>email address</strong> from their WordPress user profile.

[caption id="attachment_4502" align="aligncenter" width="784"]<a href="https://inlandempirewp.com/?attachment_id=4502"><img class="wp-image-4502 size-full" src="https://inlandempirewp.com/wp-content/uploads/2018/03/author-example.png" alt="User Profile Example" width="784" height="580" /></a> The conditional statement displays the email address and biographical info from the website's user profile.[/caption]

When the displayed page doesn't meet the conditional tag's requirements it returns a value of FALSE and continues to the else statement, in this case it does nothing.
<h3>When Conditional tags are useful</h3>
Displaying information by using <strong>TRUE</strong> or <strong>FALSE</strong> statements allows your site to respond according to specific situations. For instance, placing this code in your <a href="https://wordpress.org/themes/twentyseventeen/" target="_blank" rel="noopener">Twenty Seventeen</a> child theme's sidebar allows it to display additional information above the dynamic sidebar.

[caption id="attachment_4503" align="aligncenter" width="1096"]<a href="https://inlandempirewp.com/?attachment_id=4503"><img class="wp-image-4503 size-full" src="https://inlandempirewp.com/wp-content/uploads/2018/03/sidebar-php.jpg" alt="Sidebar Example" width="1096" height="514" /></a> Placing the custom conditional tags in the sidebar allows the code to run on all pages the sidebar appears.[/caption]

You will notice a reference to <em>pairings</em> in the screenshot above. This checks the post's tags and displays a related post using two a <a href="https://codex.wordpress.org/Class_Reference/WP_Query" target="_blank" rel="noopener">WP_Querys</a>.
<pre class="EnlighterJSRAW" data-enlighter-language="php">&lt;?php
/*
 *	Conditional Tags 
 *
 *	checks beer type and availability
 * 	displays meal pairing
 */

// When the post is tagged ipa and is in the category on-tap 
if ( has_tag( 'ipa' ) &amp;&amp; in_category( 'on-tap' ) ) {

  echo '&lt;strong&gt;Pairs well with&lt;/strong&gt;&lt;br /&gt;';

  // Display Pork menu items  
  
  // The Query -- See https://codex.wordpress.org/Class_Reference/WP_Query
  $the_query = new WP_Query(
    array(	
      'tag' =&gt; 'pork',
    )
   );

  // The Loop - Displays all pork items to go with IPAs
  if ( $the_query-&gt;have_posts() ) {

    while ( $the_query-&gt;have_posts() ) {

      $the_query-&gt;the_post();

      echo '&lt;a href="' . get_permalink() . '"&gt;' . get_the_title() . '&lt;/a&gt;&lt;br /&gt;&lt;br /&gt;';
    }

  /* Restore original Post Data */
  wp_reset_postdata();
  } else {
    // no posts found
  }

}
/*
 *	Checks food item tag and 
 *	displays it's beer pairing
 *
 */
 
if (has_tag( 'pork' ) ) {

  echo '&lt;strong&gt;Pairs well with&lt;/strong&gt;&lt;br /&gt;';

  // Display ipa tagged items  
  
  // The Query -- See https://codex.wordpress.org/Class_Reference/WP_Query
  $the_query = new WP_Query(
    array(	
      'tag' =&gt; 'ipa',
    )
   );

  // The Loop - display all ipa tagged posts
  if ( $the_query-&gt;have_posts() ) {

    while ( $the_query-&gt;have_posts() ) {

      $the_query-&gt;the_post();

      echo '&lt;a href="' . get_permalink() . '"&gt;' . get_the_title() . '&lt;/a&gt;&lt;br /&gt;&lt;br /&gt;';
    }

  /* Restore original Post Data */
  wp_reset_postdata();
  } else {
    // no posts found
  }

}</pre>
Okay, that last one was a lot of code. However, when you put both together the result is a customized sidebar responsive to the page's content.
<h4>Examples of Conditional tags at work</h4>
Using both together in the sidebar creates a mixture of results.

[gallery type="rectangular" size="medium" ids="4519,4518,4517,4516"]

This can allow you to customize your website while creating fewer new files making it easier to maintain.

<strong>If you'd like to learn more about Conditional Tags.
</strong>
<ul>
 	<li>Visit the <a href="https://codex.wordpress.org/Conditional_Tags" target="_blank" rel="noopener">Codex page for Conditional Tags</a>.</li>
 	<li>Watch <a href="https://wordpress.tv/2011/10/08/kathryn-presner-taking-control-of-your-templates-with-wordpress-conditionals/" target="_blank" rel="noopener">Kathryn Presner's presentation on Conditional Tags</a> from WordCamp Montreal.</li>
</ul>