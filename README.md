errata - multiple representations of Rails errors
=================================================

Usage
=====

```
class Banana < ActiveModel::Base
  class InvalidBananaColor < Errata::InclusionInvalidation
    default_message do
      "must be one of the following: #{valid_values.join(',')}"
    end
  end
  
  validate_inclusion_of :color, in: %w(green yellow), message: InvalidBananaColor
  
end
```
