GEMFILE

gem 'kaminari'
gem 'cancancan', '~> 1.10'

group :development, :test do
gem 'rspec-rails'
gem 'factory_girl_rails'
gem 'rails-controller-testing'
gem "faker", github: "stympy/faker"

group :development do
gem 'hirb'
gem 'interactive_editor'
gem 'awesome_print'



1. Create Rails App
rails new quiz3_redo d postgresql -T
bundle

2. Create Model:
rails db:create
rails g model idea title description:text member
rails db:migrate
