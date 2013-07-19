# Amethyst App

This is the code for the Amethyst App. The app is for creating an viewing vine channels.

## High level overview

 - Channels are owned by users, who are tied to a Twitter account. Channels
   have some basic configuration tied to them, most importantly the 'filter'
   which filters videos to only the ones the user wants on their channel.
 - Channels are populated with Videos which are fetched via the Twitter Search
   API at regular intervals (the interval is dynamic based on the activity
   of the filter).
 - Videos are displayed to users of the channel in a semi-random way, ensuring
   they mostly view recent videos.
 - What a user can and cannot do is controlled by what Plan they are on. 
   Plans are customised by admins.

## Requirements

Amethyst Channels requires the following elements:

 - Ruby 1.9.3.
 - Rails 3.2.
 - PostgreSQL
 - The ability to handle long-running processes (The default is to spawn from
   Unicorn).
 - A Fastspring account for payments & subscriptions.
 - Some Twitter application credentials.

It has been tested and deployed on Heroku, and should run there with minimum
fuss.

## Installation notes

 - Amethyst Channels was built to be run on a subdomain. If this isn't the case,
   make sure to change `config.action_dispatch.tld_length` back to 1 in
   `config/environemnts/production.rb`.
 - The first user to sign in will be an admin.

## Configuration

Configuration is done through environment variables. References to these
variables and their use are in `config/config.yml`.


