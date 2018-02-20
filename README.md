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
- What are you allowed to do (i.e. **Access Policy**)
- Mechanisms to enforce the Access Policy (i.e. **Authorization**)

## Examples of Authentication and Authorization Flows

Identification, Authentication, Access Policy and Authorization are security
concepts that equally apply to the physical and digital worlds. If you were to
enter your local bank branch they would verify:

1. Who you are by asking your name. (Identification)
2. They would verify your identity claim by checking a form of I.D. (Authentication)
3. They would verify what type of access you have. Are you allowed to withdraw
money? (Access Policy)
4. They would enforce the policy using security guards. You might be allowed to
withdraw money from your account via a teller, but you are not allowed to walk
into the safe and collect the money yourself. (Authorization)

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
