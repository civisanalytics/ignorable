[Donate to charity: water via Gittip](https://www.gittip.com/nthj/)

**Fork from [nthj/ignorable](https://github.com/nthj/ignorable/) with additional changes from [ztoolson/ignorable](https://github.com/ztoolson/ignorable)**

ignorable
=========

Ignore columns in ActiveRecord by name

Installation
============

Add this to your Gemfile:

    gem 'ignorable'

Usage
=====

```ruby
class Topic < ActiveRecord::Base
   ignore_columns :column_one, :column_two, :column_three
end
```

Note: `table_name_prefix` can cause issues, the `ignore_columns` invocation
must go after any prefix definition eg:
```ruby
class Topic < ActiveRecord::Base
   self.table_name_prefix = 'some_prefix'

   # IMPORTANT the ignore_columns invocation must go after any table_name_prefix
   ignore_columns :column_one, :column_two, :column_three
end
```


Rails Versions
==============

Tested on Rails 3.2, Rails 4.1.0, Rails 4.2.3

This gem is not needed on Rails 5.0 because an `ignored_columns` feature has
been merged in https://github.com/rails/rails/pull/21720
