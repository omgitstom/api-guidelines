# What would Tom Do (WWTD)

Below are some themes of building good APIs that aren't covered in the guidelines.  Think of this document as the hackers guide of building APIs.

## Consistency is more important than correctness

There are many videos, blogs, RFC, and dissertations on designing beautiful, useable, <insert adjective here> APIs. Ignore them all, don't be tempted. Consistency is more important than correctness.  Okta has an existing API and it is important to reuse existing patterns, names, etc.  This level of consistency enables reuse of knowledge and allows the SDKs to leverage the same code across the Okta resources.

## Think about durability over time(but with control)

It is useful to think about resources and resource models that can not only having the current use cases, but can handle future use cases without breaking backwards compatibility.  This is a useful exercise, but needs to be kept on the wheels, if it is something that isn't an immediately need post release of something on the horizon, you don't need to plan for the future.

## Use common formats

This is a something that I've seen Okta misbehave around often.  There are common formats for areas like datetime, duration, geographical positions, etc... Use them... always.  When you move away from these formats, it becomes harder for the developer to use.

## Everything is a resource or a collection of resources

When doing domain modeling it is useful to ask, "what are my resources and what is my collection?"

This helps you start to understand what are property, actions, and resource locations for the area that you are building.

## Naming is hard, documentation first design is your friend

> There are only two hard things in Computer Science: cache invalidation and naming things. --Phil Karlton

When it comes to naming things, I've found that writing the documentation of the API first helps illustrate how naming something can impact how easy or hard it is to understand.

"To modify the surname of the user, you must update the `surname` property during a POST to the `user` resource"

"To modify the surname of the user, you must update the `sn` property during a POST to the `user` resource"

Above is a simple example, but shows how an API can be self descriptive just by naming of the properties

## Partial updates with POST is more important than full updates with PUT

Okta is a big offender here.  Full resource replacement by PUT isn't usually what the developer is trying to do.  Resource Creation time is when they provide all required information, afterwards, it is partial updates via POST. The minimal thing that you would need to support in an API is resource creation via POST to a collection resource, then updates via POST to the resource itself.

## When a new pattern is needed, don't recreate the wheel

There are a lot of times when a new pattern is needed.  In that case, stackoverflow and other companies are your friends. Learn from other person.  Okta's problems are not unique.

##  Goodluck!

I wish you all the best. -- Tom
