# Register-ACF-Block

```php
add_action('acf/init', 'my_acf_blocks_init');
function my_acf_blocks_init() {

    // Check function exists.
    if( function_exists('acf_register_block_type') ) {

        // Register a restricted block.
	acf_register_block_type(array(
	    'name'		=> 'name',
	    'title'		=> 'Title',
	    'description'	=> 'Here is a description.',
	    'category'		=> 'formatting',
	    'mode'		=> 'preview',
	    'icon'              => 'star-filled',
	    'keywords'          => array( 'keyword, wd, acf' ),
	    'post_type'         => array( 'post', 'page' ),
	    'supports'		=> array(
		'align' => true,
		'mode' => false,
		'__experimental_jsx' 	=> true // <innerBlocks />
	    ),
            'render_callback'	=> 'rod_acf_block_render_callback',
            //'enqueue_script'    => get_stylesheet_directory_uri() . '/blocks/js/hero-block.js',
	));
    }
}
```
