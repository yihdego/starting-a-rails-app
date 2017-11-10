# starting-a-rails-app
Instructions to initialize a rails app to my preferred settings.

1. Generate a new Rails app
  ```
  rails new [APP-NAME] -T -d postgresql --skip-turbolinks
  ```

2. Make an initial commit
  ```
  cd [APP-NAME]
  git init
  git add .
  git commit -m "Initial commit. Rails boilerplate."
  ```

3. Remove coffee script
  remove coffee-rails from Gemfile

  **Gemfile**

  ~~gem 'coffee-rails'~~

  **Terminal**
  ```
  bundle install
  git add .
  git commit -m "Remove coffee-rails."
  ```
  
4. Add HTTP Client and normalize to css
  add httparty and normalize-rails to Gemfile
  
   **Gemfile**
    # HTTP Client
    gem 'httparty'
    # Akin to normalize css file
    gem 'normalize-rails'


5. Add testing Gems.
  Add gem rspec-rails (and faker usually) to the development, test group toward the bottom of the Gemfile.

  **Gemfile**
  ```ruby
  group :development, :test do
    ...
    gem 'dotenv-rails'
  end
  ```
  
  ```ruby  
    group :test do
    ...
    gem 'rspec-rails'
    gem 'simplecov', require: false
    gem 'rails-controller-testing'
    gem 'shoulda-matchers'
    gem 'faker'
    gem 'capybara'
    gem 'poltergeist'
    gem 'webmock'
    gem "factory_bot_rails", "~> 4.0"
    gem 'database_cleaner'
  end
  ```

  **Terminal**
  ```
  bundle install
  rails g rspec:install
  git add .
  git commit -m "Set up rspec."
  ```

6. Add Github remote address
  Back in your terminal inside your project folder

  ```
  git remote add origin https://github.com/[ORGANIZATION]/[APP-NAME].git
  git push -u origin master
  ```

7. Start adding your own code.
  Apart from ensuring all your tools are in place, doing all the install steps up front gives you a good point to compare back to later
