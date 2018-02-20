# Introduction to Authentication and Authorization

![Sample bank account web interface](https://curriculum-content.s3.amazonaws.com/web-development/bank_account_sample.png)

Imagine you shared (by accident!) the URL to your bank’s web application. Would
you expect that anyone who followed the link should be able to see that you
paid an extremely expensive (but organic) $9.50 on a Greenleaf Juice? We hope
that you, like us, would find that an _extremely_ undesirable outcome!
Thankfully that's not how bank web applications work, thankfully!

But why is this so? Why can some URLs be followed to view a page (say the IMDB
page of the 1980 _magnum opus_ "[Flash Gordon][FG]") and have the same
experience, but others cannot?  How are banks able to provide you full access
to your account information while limiting what everyone else can see? It turns
out this is a pretty common problem which anyone who is building a web
application will likely face. We'll be exploring this "who gets to see what"
problem in this lesson.

## Breaking Down the Authentication and Authorization Problem

We can divide the "who can see what" problem into four smaller, but related
problems:

- Who are you (i.e. **Identification**)
- Are you who you claim to be (i.e. **Authentication**)
- What is a given _role_ allowed to do (i.e. **Access Policy**)
- Mechanisms to enforce the Access Policy (i.e. **Authorization**)

## Examples of Authentication and Authorization Flows

**Identification**, **Authentication**, **Access Policy** and **Authorization**
are security concepts that apply equally to the physical and digital worlds. If
you were to enter your local bank branch they would verify:

1. Assert who you are by stating your name and showing an ID
   (**Identification**)
2. Verify your identity claim by verifying you possess a secret that only the
   "real you" would know and which had been established prior to this moment.
   This might be a password, matching signature, [knowledge of bedroom furniture][odyssey],   etc. (**Authentication**)
3. _Interlude_ At this point the bank knows that they are dealing with a
   _verified entity_. From the perspective of their system, all _verified
   entities_ act with respect to a _role_. _Roles_ can be expressed with the
   formulation _As an_. Implicitly, at point of **Authentication** your
   collection of _roles_ is also retrived.
4. You then proceed to withdraw enough money for another delicious Greenleaf
   juice. At this point the **Access Policy** ("_As an_ +owner+ of an account,
   the +owner+ is permitted to withdraw money from that account provided that the
   amount to withdraw does not reduce the balance to $0.00 or less") is
   implemented in an activity known as **Authorization**.
5. You then walk up to the vault and try to go in. Your _roles_ +owner+ and
   +customer+ have a "NO ACCESS" policy as relates to the bank's vault. As
   such, you will _not_ be **Authorized** and will probably earn the new role of
   +attempted robber+.

Let's apply this thinking to a web login.

When you access your bank account on the web you will:

1. Enter a username. That is an identity claim. (Identification)
2. Enter a password. You are providing proof of your identity claim.
(Authentication)
3. You will be granted certain privileges based on your identity. (Access Policy)
4. Sprinkled throughout the web application, your bank will have checks to
enforce the Access Policy. You will not be allowed to alter your balance and add $1,000,000.

## Defining Key Authentication and Authorization Terms

We can define the four security concepts that help us answer the "who can see
what" questions as:

- **Identification**: Obtaining and identity claim from the user. (e.g., my
email is,  my name is)

- **Authentication**: The process of verifying the identity claim of a user.

- **Access Policy**: An access policy based on the identities and attributes of
the resource being accessed and of the user requesting access.

- **Authorization**: Access privileges granted to a user or the act of granting
those privileges.

## Section Objectives

Over the course of this section, you will learn how to build a basic
implementation of these four security concepts in a Ruby on Rails application.

[FG]: http://www.imdb.com/title/tt0080745/
[odyssey]: http://classics.mit.edu/Homer/odyssey.23.xxiii.html#151
