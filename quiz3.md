1. rails new quiz3 -d postgresql -T
2. cd quiz3
3. rails db:create
4. rails g controller idea
5. in routes.rb
```
resources :ideas

root 'ideas#index'
``
6. create index.html.erb in views/ideas
7. rails g model title body
8. rails db:migrate

USER AUTHENTICATION
9. rails g model user first_name last_name email password_digest
10. in the migration file, add this after the whole def method
```
    add_index :users, :email
```
- rails db:migrate
- rails g controller users
- in routes.rb
```
resources :users, only: [:new, :create]
```
- create new.html.erb file in views/users, put in the sign up form.
- in application.html.erb in views/layouts
```
    <%= link_to "Sign Up", new_user_path  %>
```    
- in users_controller.rb, define the new action
```

```

application_controller.rb
```
def user_signed_in?
session[:user_id].present?
end
helper_method :user_signed_in?


def current_user
  @current_user ||= User.find session[:user_id] if user_signed_in?
end
helper_method :current_user

def authenticate_user!
redirect_to new_session_path unless user_signed_in?
end

```
- in user.rb
```
  has_secure_password

```
