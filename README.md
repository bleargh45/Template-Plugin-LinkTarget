# NAME

Template::Plugin::LinkTarget - Template Toolkit filter to add "target" attribute to all HTML links

# SYNOPSIS

```
[% USE LinkTarget(target="_blank" exclude=['www.example.com']) %]
...
[% FILTER linktarget %]
  <a href="http://www.google.com/">Google</a>
[% END %]
...
[% text | linktarget %]
```

# DESCRIPTION

`Template::Plugin::LinkTarget` is a filter plugin for `Template::Toolkit`,
which adds a `target` attribute to all HTML links found in the filtered text.

Through the use of the `exclude` option, you can specify URLs that are _not_
given a new `target` attribute.  This can be used to set up a filter that
leaves internal links alone but that sets up external links to open in a new
browser window.  `exclude` accepts a list of regular expressions, so you can
be as elaborate as you'd like.

The `target` option specifies what target you'd like to give to links,
defaulting to "\_blank".

# METHODS

- init()

    Initializes the template plugin.

- filter($text, $args, $conf)

    Filters the given text, and adds the "target" attribute to links.

# AUTHOR

Graham TerMarsch (cpan@howlingfrog.com)

# COPYRIGHT

Copyright (C) 2008, Graham TerMarsch.  All Rights Reserved.

This is free software; you can redistribute it and/or modify it under the same
terms as Perl itself.

# SEE ALSO

[Template::Plugin::Filter](https://metacpan.org/pod/Template%3A%3APlugin%3A%3AFilter).
