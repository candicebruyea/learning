
# Devel Content Module

This module generates random content for your Drupal website.

1. Create content type for which you'd like to generate content.

2. Download Devel module on drupal.org
   * Search for Devel on drupal.org/project/devel
   * Find terminal command to install devel and enter it in terminal (in root directory for project).
     * A devel folder should exist in the contrib folder for modules. 
     * Enter Drush command to enable the module


    drush en devel

3. In the backend UI, click Extend and search for Devel. You should see it there under Development, with checkbox checked.
4. Enable the devel_generate module

   
    drush en devel_generate
5. In backend UI, click Configuration - Devel Generate - Generate Content
6. Select the content type you want to use 
7. Enter a number for how many nodes you'd like to make, Max # of words in title.
8. Click Generate button
    * You should see green banner stating number of nodes created.
9. Check website to make sure you can see the content.

