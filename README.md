# NAME

File::Compressible - determine if a mime type is compressible

# SYNOPSIS

    use File::Compressible 'compressible;
    use File::Type;
    ...
    my $ft = File::Type->new();
    for my $file (@files) {
      my $type = checktype_filename($file);
      next unless $type;
      next unless compressible($type);
      # do some compression magic!
    }



# DESCRIPTION

File::Compressible supplies one exportable function, `compressible`, which takes
a mime type and returns true if it is compressible, undef if not.

Compressible mime types are stored in a package variable,
`@File::Compressible::compressible`.  It is concidered okay to modify this list
and future versioins will maintain this.  A second package variable contains
precompiled regular expressions that are tested against passed mime types, it
is named `@File::Compressible::compressible_re`.

# AUTHOR

Mike Greb <michael@thegrebs.com>

# COPYRIGHT

Copyright 2013- Mike Greb

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO

[File::Type](http://search.cpan.org/perldoc?File::Type)
