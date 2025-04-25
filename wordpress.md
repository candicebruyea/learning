# Wordpress Basics

## Creating a New Theme

Location: wp-content/themes
1. make a new folder for your theme
2. add index.php
3. add style.css
4. Add a comment to style.css to share theme details

Comment example:

    /* 
    Theme Name: Fictional University
    Author: Candice
    Version: 1.0 
    */

5. Add a 1200 x 900 image file for the theme to the new theme folder, named screenshot.png 
6. Delete all the other generic themes from the themes folder.

## Files needed in a theme
Template Files
* index.php - the main code
* single.php - code followed for single posts
* page.php - code followed for single pages
* header.php - code followed for the header
* footer.php - code followed for the footer
Private Files
* functions.php - can have a convo with the wordpress system.
Other Files
* screenshot.png - screenshot of the theme
* style.css - css styling

## PHP Functions

Tell Wordpress to load our CSS file via functions.php:

    <?php wp_head(); ?>

___

Get Header and Footer:

    get_header();
    get_footer();

___

Show as many posts as we have:

        while(have_posts()) {
        the_post();
        }

___

The post title and post content:

    the_title();
    the_content();

___

A typical array of posts:

    <?php
        while(have_posts()) {
        the_post(); ?>
        <h2><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></h2>
        <?php the_content(); ?>
        <hr>
            <?php }
    ?>

A typical array of pages:

    <?php 
    get_header();

    while(have_posts()) {
        the_post(); ?>
        <h2><?php the_title(); ?></h2>
        <?php the_content(); ?>
    <?php }

    get_footer();
    ?>

___

Give wordpress control of our head, load whatever it needs to load there.

    <head>
        <?php wp_head(); ?>
    </head>

___

To tell Wordpress an instruction, use the add_action function. It will have two arguments: 
* the first tells what type of action we want it to do
* the second is the name of the function we want to run.

Example:

    add_action('a', 'b');

___

Tell Wordpress to load our CSS file (added to functions.php)
Functions used are:
* wp_enqueue_style (Enqueues a CSS stylesheet)
    * get_stylesheet_uri (retrieves stylesheet URI for the active theme)
* wp_enqueue_scripts (tells action type: load CSS or javascript files)
* add_action (an instruction for wordpress)

Example
    
    <?php 

    function choose_a_name() {
        wp_enqueue_style('choose_stylesheet_nickname', get_stylesheet_uri());
    }

        add_action('wp_enqueue_scripts', 'choose_a_name');
    ?>

___

Tell Wordpress to run any scripts or data before the closing body tag. 
* Add this to footer.php, along with the closing body and html tags (remove those from index.php)

Example

    <?php wp_footer(); ?>
    </body>
    </html>