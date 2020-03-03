# Saber-si-estoy-en-el-blog-Wordpress

```php
/**
 * WordPress' missing is_blog_page() function.  Determines if the currently viewed page is
 * one of the blog pages, including the blog home page, archive, category/tag, author, or single
 * post pages.
 *
 * @return bool
 */
function is_blog_page()
{
    global $post;

    // Post type must be 'post'.
    $post_type = get_post_type($post);

    // Check all blog-related conditional tags, as well as the current post type, 
    // to determine if we're viewing a blog page.
    return ( $post_type === 'post' ) && ( is_home() || is_archive() || is_single() );
}
```
