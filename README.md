# My Starter App

## What’s included in this app
+ Gems
  + Basic pages
  + Created Home (root), About, and Contact pages
  + Set routes to intuitive routing (eg. app.com/contact)
+ Bootstrap
  + Imported in scss file, required in jquery file
  + Added viewport meta tag to layouts/application file to ensure responsiveness on mobile devices
+ Devise
  + Installed and generated views
  + Removed (commented out) password confirmation from new registration form (which removes the requirement)
  + Created User model
  + Changed “Log in” to “Sign in” for consistency and changed error message (from “1 error” to “An error”)
+ App Layout
  + Rendered partials in layouts/application file:
    + Alert partial
     + Navigation partial with links to Basic pages, Devise views, and select resource views

## Customization instructions
+ Navigation Bar
  + Edit “App Name” & links
+ Devise
  + In config/environments/production.rb (right before end of file): config.action_mailer.default_url_options = { host:  'http://actualhostname.com/' }
  + Add other variables to user migration file before rake db:migrate (or in a new migration file)
  + Customize error messages in config/locales/devise.en.yml and links in app/views/devise/shared/_links.erb
  + If want to require email confirmation in order to create an account, add :confirmable to the list of devise "modules" (to the right of :validatable). This instructs Devise to send a confirmation email when a new user signs up
     + Do this before adding users, or add a special migration. Otherwise, some users will be unconfirmed in the system.  
  + Note: If you want emails to be sent out, you must set up Sendgrid (and Heroku or another hosting service)

## Setup instructions
1. Clone git repository
  * git clone https://github.com/comfortcode/starter-app.git
2. Set new remote
  * git remote set-url origin git@github.com:comfortcode/rentals.git
3. Install gems and dependencies
  * bundle install
4. Create db and migrate schema
  * rake db:migrate
5. Run your application
  * rails s

## Ideas for expanding this app
+ Removing Extraneous Gems
+ Bootstrap Styling for Devise Forms
+ Reformatting Alerts to Appear Without Padding
+ Pundit Permissions
+ Outgoing Email Setup (Sendgrid, and a welcome email)
+ Contact Form
+ Page Layouts for Basic Pages