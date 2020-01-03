# `Date`, `DateTime` API in Ruby

### Using `Date.current` vs `Date.today`

`Date.current` is the preferred option as it utilises the time zone where it is set; use for time-zone sensitive operations & as rule of thumb.

Always use `Date.current` for comparisons.
