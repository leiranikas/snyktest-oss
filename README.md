# utm-playground

The UTM Playground is a demo web application to experiment with UTMs and the automation that can be driven by their use.
The goal of this app is to provide Marketing Operations with a place where they can experiment with UTMs independently.

## How to run the app
The app is hosted in Snyk's Heroku Enterprise account (https://dashboard.heroku.com/apps/snyk-utm-playground)
Changes made to this project and committed to the `Master` branch are automatically deployed to Heroku and immediately available on https://utm-playground.snyk-mops.com/

## Disclaimers and rules
1. The app requires a @snyk.io login (implemented with Google oAuth). Any content added to this app must be behind the login and not made public without approval from the Security team
2. This app is intended for experimentation only, and should not be used to host any production activities
3. Any code to be deployed to the Master Branch, must be code reviewed. Pull requests are mandatory in order to deploy code

## Coming Soon
- CI pipeline with CircleCI for testing and build activities before deploy
- Separate branch for production deployment to prevent changes from being deployed without review, test and build


## Contributing to this project ## 
This app is written in Ruby, using the Hanami framework for quick implementation. 
To get started, follow the instructions to set up your environment and clone this repository to your local environment and follow the instructions below to run the project locally

## Environment Setup (Mac OSX)
### Recomended pre-setup
- https://iterm2.com/ - iTerm, a MacOS terminal replacement
- https://github.com/sorin-ionescu/prezto - A terminal configuration and zsh for a richer terminal experience
- Install your favorite IDE or text editor (https://www.sublimetext.com/, https://atom.io/, https://www.jetbrains.com/ruby/ etc.)

### Install Xcode Command Line Tools
```
git --version
```
If you don't have it installed already, it will prompt you to install. Follow the instructions.

### Install Homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Ruby and RVM
While Mac OSX comes with a version of Ruby pre-installed, it's recommended to install a fresh version from Homebrew in order to support multiple Ruby environments with different versions in parallel
`\curl -sSL https://get.rvm.io | bash -s stable`
`rvm install ruby-2.7`

### Install PortgresQL ###
```
brew install postgresql
brew services start postgresql
psql postgres
QUIT
```

### Install the Heroku CLI ###
`brew tap heroku/brew && brew install heroku`

### Clone the repository ###
```
git clone git@github.com:snyk-bpo/utm-playground.git
cd utm-playground
```

### Install dependencies
From the project folder, run `bundle install` to install all dependencies
Note that these dependencies will live under their own Gemset, and will not override any other ruby projects you may be working on


## Running project Locally (Does not require Google Login)
How to prepare (create and migrate) DB for `development` and `test` environments:

```
% bundle exec hanami db prepare

% HANAMI_ENV=test bundle exec hanami db prepare
```

How to run tests:

```
% bundle exec rake
```

How to run the development console:

```
% bundle exec hanami console
```

How to run the development server:

```
% bundle exec hanami server
```

Your app will be accessible locally on http://localhost:2300/

Explore Hanami [guides](https://guides.hanamirb.org/), [API docs](http://docs.hanamirb.org/1.3.4/), or jump in [chat](http://chat.hanamirb.org) for help. Enjoy! 🌸

