# Twitter Clone

**Notes**
Created: April 10, 2022

*April 15, 2022:*<br>
This was build using Rails 7 and the devise gem for authentication.  Devise has not been updated to support rails 7 so certain workarounds were needed. Edit these devise views: `registrations/new` and `sessions/new`
by changing 

```form_for(resource, as: resource_name, url: session_path(resource_name) ) do |f|```<br>
to<br>
```form_for(resource, as: resource_name, html: {'data-turbo' => "false"}, url: session_path(resource_name) ) do |f|```<br>


in addition, for your logout links use Rails button_to instead of link_to.

```, method: :delete, 'data-turbo': false```<br>
or<br>
```data: { turbo: false }```<br>

[Stackoverflow source](https://stackoverflow.com/questions/66615478/turbo-rails-with-devise-does-not-redirect-consistently-rails-6-1-3-devise-4-7-3)
