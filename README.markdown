Purpose
=======
Behave like resource provides an easy way to test your RESTful controllers.
It is best used in combination mit make_resourceful or resource_controller.
Use it to test those actions you barely touch.


Installation
============
RSPEC
-----
only works with [rspec](http://github.com/dchelimsky/rspec) and [rspec-rails](http://github.com/dchelimsky/rspec-rails/tree/master)

MOCHA
-----
tested with [Mocha](http://mocha.rubyforge.org/) for mocking only.
 
Finally
-------
<code>script/plugin install git://github.com/grosser/behave_like_resorce.git</code>

add to spec_helper.rb(after rspec is loaded)

    require "vendor/plugins/behave_like_resource/require_me" 


Test Setup
==========

    describe UsersController do
      before :each do
        login_as :quentin #if your controllers need login
        @item = @user = stub_model(User)#or anything else that has a to_param method
      end
      
      behave_like_resource
    end 