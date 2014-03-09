wp_query_views
==============

A wrapper around WP_Query to build Views and expose filters

Random thoughts/notes:

Each View is going to be output as a custom shortcode. This is simple and allows them to be used in any page or widget.
We will need options on View creation like "submit path". This way the View can have an exposed form point somewhere else.
Display form only shortcode option (sidebar quick search maybe?)

Propsed Architecture

wp_query_views.php - Plugin class. The glue that puts everything together. Registers handlers and other common items.
- handlers
-- query and theme handlers - base classes to be overridden
- common
-- common includes. Such as classes for outputting theme into template files. Maybe base class for creating HTML markup?
- theme
-- admin -- templates used for admin. apply_filters for altering templates? NOTE: each "View" will be an instance of a custom post type?
-- display -- templates used fordisplay. apply_filters for altering templates?
- admin
-- files for registering post types etc
-- settings classes. Abstract class to be overridden?
-- js - will needs lotsa stuff for the admin screens
