SpreeBetterBreadcrumbs
======================

Just an update to the spree breadcrumbs to provide more intuitive usage of breadcrumbs.  The products path and taxons path are seperate, and the breadcrumbs will also display the product name at the end.

An additional helper method has been added to provide a path to the last visited breadcrumb (either a taxon or the products path), to allow linking back to the last specific area the user was in.  This is useful when a user adds something to their cart, they can be linked back to the last taxon they were browsing.

Installation
============

Here's how to install spree_better_breadcrumbs into your existing spree site AFTER you've installed Spree:

Add the following to your Gemfile:

    gem 'spree_better_breadcrumbs', github: 'jtapia/spree_better_breadcrumbs'

Make your bundle happy:

    bundle install

Now run the generator:

    rails g spree_better_breadcrumbs:install

And reboot your server:

    rails s

You should be up and running now!

Example
=======

Breadcrumbs now take an addition parameter, a product as parameter two:

<%=breadcrumbs(@taxon, @product, optional_seperator_string)%>

For backwards compatibility the optional separator string can also be passed as the second parameter, but doing so limits some of the functionality of the breadcrumbs.

To get the path to the last breadcrumb use:

<%=link_to 'back', last_crumb_path%>
