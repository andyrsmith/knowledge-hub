# Rails Routes

To set up a new route to an action in a controller put the following in routes.rb file.

```
get 'pages/home', to: 'pages#home'
```

Maps the url pages/home to the home action of the pages controller

Set root of page

```
root 'pages#home'
```

Sets the root / url to home action of the pages controller

 Create standard routes for a controller

```
resources :signup
```

This will create routes like signups#index, signups#create, and so on for you so you don't have to define them each individually

View routes in your app by the rails routes command

```
bundle exec rails routes
```

