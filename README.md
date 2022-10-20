# THINGS IN HERE

## GEMS

```
gem "sassc-rails"
gem 'simple_form'
gem 'devise'
# gem 'bootstrap-sass'
```
- sassc for scss
- didnt use bootstrap
- devise set for turbo, rails 7
- from: https://dev.to/efocoder/how-to-use-devise-with-turbo-in-rails-7-9n9

## MODELS
- devise user
- user has many items
- items have a completed at patch as datetime

```
  resources :items do
    member do
      patch :complete
    end
  end
```
- and addded the method in the controller

```
  def complete
    @item = Item.find(params[:id])
    @item.update_attribute(:completed_at, Time.now)
    redirect_to root_path
  end
```

## OTHER
- used custom stylings
- imported fonts via the app.scss

```
@import url(http://fonts.googleapis.com/css?family=Oswald:400,700|Merriweather:400,300);
```