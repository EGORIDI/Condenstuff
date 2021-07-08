---
layout: post
title:  "Portefeuille - a stock-tracker social network app in Ruby on Rails"
date:   2021-07-08 14:26:53 -0300
categories: jekyll update
---

![Finance-tracker](https://res.cloudinary.com/practicaldev/image/fetch/s--XTN9fuI---/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hxgksaphtiua8n1h2kfn.jpg)

I always thought that developing for finance would require mostly C or other compiled, statically typed language, especially for dealing with the incoming data from the stock market. Nevertheless, I have just accomplished a basic skeleton app (sort of an MVP - a Minimum Viable Product) for a social network of stock tracking using only Ruby on Rails.

Of course, it required some Javascript (not my thing) for the Ajax forms responses, some HTML for the pages and basic CSS for formatting, yet it was essentially all written in Ruby. And it got pretty fast, I dare to say.

The first challenge was to have an incoming data flow from stock exchanges. Here the Ruby community shines, for there's always a gem for everything. Using the IEX Cloud Finance API ruby client, as they have a simple way to integrate with my app, provided a plethora of data. They also supply free test data to developers. As all I needed to start was the ticker, company name and last price, while not working with up-to-date data, I got all the tubes connected and working in no time.

A delicate point was to deal with credentials. Rails 6 provides an elegant way of doing it. There's a master key in your app and all the others, such as AWS and, in this case, IEX, can be safely stored encrypted in the code, without using environmental variables etc.

From this point on, it was more a matter of choosing a decent layout, creating the necessary entities and table relationships to reflect each user choice of stocks and other users to follow and steal stock ideas from.

Follow? Did I tell you it is a social network? Yes, and quite an elementary one. But it gave me several ideas regarding the relationship patterns among users.

For instance: In this case, I chose to allow users to anonymously follow whomever they wanted, without any need of consent (therefore, everything so far is public to the app community) but also without affecting the followed user. And it feels kind of a libertarian thing. People may be interested in you while you may not follow them, even care (or know) about it. This relation is called 'friendship' in the app model. But I may change that, because...

On the other hand, I plan to create another kind of relationship that should be univocal on both sides, more personal and mutually consensual. More close to people there are already or consider becoming friends. Perhaps even allowing mutual conversation in such a case (integrating a real-time chat app such as my 'Recadin', which unfortunately isn't yet public).

Anyway, it allowed me to reflect on the various kinds of relationships possible on social networking and how I may be developing these in terms of models and controllers.

On a side note, the very User model is bound by Devise, the great authentication gem that I used. Looks kind of overkill for this simple app, though, but it performs gracefully and brings all you need just out of the box.

Also, as I've got some finance and banking experience, I got the chance of thinking about financial assets more on an app way and less on a spreadsheet logic, which is quite interesting. Also gave me the ideas of adding all sort of finance features to the app, starting with asset allocation (weighing your portfolio), betas and various financial measures.

The code can go better, I may improve it soon, but I already liked the way it already is. Pretty neat, yeah? ;)

Check it out in my GitHub repo:
[Portefeuille](https://github.com/EGORIDI/finance-tracker)

And play with it on production if you like:
[Portefeuille on production](https://bearded-goose-39137.herokuapp.com)

Finally, I only did this app because of the relevant Ruby on Rails Udemy course I am doing now. I highly recommend it:

[The Complete Ruby on Rails Developer Course](https://www.udemy.com/share/1013z6BEQSdVxbRnw=/)

