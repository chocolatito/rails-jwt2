# Rails API + JWT Authentication

> ***based in tutorial: [Rails API + JWT Authentication](https://medium.com/binar-academy/rails-api-jwt-authentication-a04503ea3248)***

---
```sh
rails new rails-jwt2 --api
cd rails-jwt2
```
---
> ___./Gemfile___
```ruby
# Use Json Web Token (JWT) for token based authentication
gem 'jwt'
# Use ActiveModel has_secure_password
gem 'bcrypt', '~> 3.1.7'
```

```sh
bundle
```
---
> ___./config/routes.rb___
```ruby
Rails.application.routes.draw do
  resources :users, param: :_username
  post '/auth/login', to: 'authentication#login'
  get '/*a', to: 'application#not_found'
end
```

---
```sh
rails g model user username:string email:string password_digest:string
rails g controller users
rails g controller authentication
```
