=== Post Widgets ===
Contributors: johnciacia 
Tags: widget, sidebar, post
Requires at least: 3.2.1
Tested up to: 3.4.1
Stable tag: 1.0

This plugin gives you post level control of the widgets that appear in each of your sidebars.


== Installation ==

Extract the zip file and just drop the contents in the wp-content/plugins/ directory of your WordPress installation and then activate the Plugin from Plugins page.

== Frequently Asked Questions ==

= The Sidebar Admin metabox only appears on the Pages post type. How can I use this plugin for other post types? =

You may use the `post_widget_post_types` filter to add additional register this plugin with additional post types.

`add_filter( 'post_widget_post_types', 'add_post_types' );
function add_post_types( $post_types ) {
	$types = $post_types;
	$types[] = 'post';
	$types[] = 'my-custom-post-type';
	return $types;
}`

= Can I override the default sidebar arguments? =
There are several filters that give you full control of the sidebars. You can use the `post_widgets_default_sidebar_args` filter to globally set the arguments for all sidebars. You can control the arguments based on the sidebar itself using the `post_widgets_default_sidebar_args-{$sidebar}` filter (where {$sidebar} is the sidebar id). You can also control the sidebars on a post by post basis using the `post_widgets_default_sidebar_args-{$post_name}` filter (where {$post_name} is the post slug). The filters are applied in the following order:

1. post_widgets_default_sidebar_args
1. post_widgets_default_sidebar_args-{$sidebar}
1. post_widgets_default_sidebar_args-{$post_name}
1. post_widgets_default_sidebar_args-{$sidebar}-{$post_name}

== Screenshots ==

1. Sidebar Admin metabox that appears on post types registered with this plugin.
2. Sidebar Admin metabox with active widgets in the 'Footer Area One' sidebar.

== Changelog ==

= 1.0 =
Initial release