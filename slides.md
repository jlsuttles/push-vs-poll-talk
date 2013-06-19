# push-vs-pull-talk

!SLIDE

# Polling: It's Good Enough for the WWW & It's Good Enough for You

!SLIDE

# Jessica Lynn Suttles
## @jlsuttles
### jlsuttles.com
#### Santa Monica, CA

!SLIDE

# G5 (Search Marketing)
## @g5platform
### http://getg5.com
#### Bend, OR

!SLIDE

# Mr. Manager™ Shane Becker
## @veganstraightedge
### iamshane.com

!SLIDE

# Steve Klabnik
## @steveklabnik
### steveklabnik.com

!SLIDE

# The Farmhouse Podcast
## Push vs "Pull"
### Shane Becker & Steve Klabnik
#### [http://farmhouse.la/podcast/2](http://farmhouse.la/podcast/2)

!SLIDE

# Polling: It's Good Enough for the WWW & It's Good Enough for You

!SLIDE

# Words are hard.

!SLIDE

# Words are difficult.

!SLIDE

# Words are confusing.

!SLIDE

# So let's start with some definitions.

!SLIDE

# Push is a style of communication where the request for a given transaction is _initiated by the publisher_ of data.

!SLIDE

# Pull is a style of communication where the request for a given transaction is _initiated by the consumer_ of data.

!SLIDE

# Push & pull are antonyms.

!SLIDE

# Push & pull indicate direction of communication.

!SLIDE

# Polling is a style of communication where _multiple pulls_ are used to sample server state at an interval.

!SLIDE

# Polling indicates a continual process that makes use of multiple pulls.

!SLIDE

# Historically if two components needed to talk on a system they used polling.

!SLIDE

# So when it came time to design the web it was natural to use a polling model.

!SLIDE

# And so the web was built on the _client-server model_.

!SLIDE

# This model assigns one of two roles to the computers in a network: Client or Server.

!SLIDE

# A server is a computer system that selectively shares its resources.

!SLIDE

# A client is a computer or computer program that _initiates contact with a server_ in order to make use of a resource.

!SLIDE

# The web is one of the largest and most successful software projects, so there must be something to this model.

!SLIDE

# But lately people have been moving to a push model.

!SLIDE

# Push feels natural, but it can be expensive.

!SLIDE

# Expense can refer to server requests or server resources.

!SLIDE

# Push requests scale linearly.

!SLIDE

# When using push the server needs to initiate one request per client.

!SLIDE

# One request per client requires a lot of server resources.

!SLIDE

# Let's imagine @jlsuttles & @ashedryden each have 100 Twitter followers.

!SLIDE

Wow @jlsuttles is giving a great talk right now!

Thank you, @ashedryden! You're too kind. <3 I can't wait for your keynote tomorrow!

.@jlsuttles me neither! It's at 9am sharp. Don't be late!

!SLIDE

# Push requires a minimum of 300 requests.

!SLIDE

# That's a lot of requests! Imagine if we had 1,000,000 Twitter followers.

!SLIDE

# An advantage of push is that it can seem instantaneous.

!SLIDE

# But the more push requests that need to be sent, the harder it is to make them all seem instantaneous.

!SLIDE

# Polling _can_ scale better than linear.*

!SLIDE

Wow @jlsuttles is giving a great talk right now!

Thank you, @ashedryden! You're too kind. <3 I can't wait for your keynote tomorrow!

.@jlsuttles me neither! It's at 9am sharp. Don't be late!

!SLIDE

# Polling requires the server to respond to a minimum of 0 requests.

!SLIDE

# Pull requests are cheap so it's easy to do many at the same time.

!SLIDE

# *Polling without server side caching can be very expensive.

!SLIDE

# HTTP Conditional Get

!SLIDE

# The server sends a `Last-Modified` header.

!SLIDE

# The client sends a `If-Modified-Since` header.

!SLIDE

# If the server has new data it sends back a `200 OK` response code and data.

!SLIDE

# If the server doesn't have new data it sends back a `304 Not Modified` response code and no data.

!SLIDE

# Memcache

!SLIDE

# Every pull hits the cache everytime, so no one is ever hitting the server.

!SLIDE

# The server effectively pushes to the cache to update it, which is inexpensive because the server is guaranteed to have one client.

!SLIDE

# Error Handling

!SLIDE

# Relying soley on push requires the server to keep track of failures and retries for all subscribers.

!SLIDE

# It is much more reasonable less complex for a client to keep track of their own failures and retries.

!SLIDE

# You don't have to choose just push or just polling.

!SLIDE

# PubSubHubBub

!SLIDE

# A subscriber initially pulls a feed from a publisher.

!SLIDE

# If the feed references a hub, the subscriber can subscribe to the feed on the hub.

!SLIDE

# Publishers post notifications to the hub whenever they publish something.

!SLIDE

# The hub then directly notifies the subscriber when the feed is updated.

!SLIDE

# So the publisher notifies the hub, then the hub notifies the subscriber.

!SLIDE

# OStatus is a micro blogging protocol that is built ontop of PubHubSubBub
# rstat.us is an open source prject that uses OStatus.

!SLIDE

# Is push ever necessary?

!SLIDES

# Push is necessary when you need low latency updates with high frequency.

!SLIDE

# Chat

!SLIDE

# Campfire uses polling with a 2 second interval.

!SLIDE

# Multiplayer Interactive Games

!SLIDE

# Chess doesn't need push. First person shooters probably need push.

!SLIDE

# Polling is the sound engineering decision.

!SLIDE

# Push a new and interesting solution.

!SLIDE

# If you're a start up you are probably doing new and exciting things!

!SLIDE

# It is entirely possible there are applications that need push that we don't know about yet.

!SLIDE

# But make sure you really need it because if your startup succeeds its going to be pricey to scale.

!SLIDE

# Thank you!
## <3 @jlsuttles
