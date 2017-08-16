---
comments: true
---
Jekyll is awesome, isn't it? But I noticed one annoyance when creating a new post.
Basically, in Jekyll we have to name file with format *YYYY-MM-DD-tittle-blah-blah.md* when creating a new post.
Wouldn't it be quicker and convenient if  jekyll provide a quick command to create new post and generate the file name automatically?
I was wondering if the command itself exists because i'm a newcomer, if not then I'll try to write it by myself.
We shouldn't reinvent the wheel right?

So, quick googling led me to this [discussion](https://github.com/jekyll/jekyll/issues/2254).
It's very long discussion and was actually started since 2014 (glad it wasn't only me that feel the annoyance).
I have no time to read all the discussion and quickly scrolled to the most bottom part of the discussion.
I found that there is some resistance to include the command into jekyll repository directly.
Fortunately, a nice guy from github decided to make plugin for it.
And here it is ,  [jekyll-compose](https://github.com/jekyll/jekyll-compose).
A plugin to quick compose draft and publish it.

So basically what we have to do is to include the plugin into our application's Gemfile like this.

{% highlight ruby %}
gem 'jekyll-compose', group: [:jekyll_plugins]
{% endhighlight %}

And then execute `bundle install`.

For creating a new draft just execute `bundle exec jekyll draft "New draft title"`.

Then for publishing the draft just execute `bundle exec jekyll publish _drafts/new-draft.md`.
It'll move the draft file into \_post directory and prepend current date into the file name. Cool!!
Setting the date can be performed using `--date YYYY-MM-DD` for command above.
You could also generate post and page, and unpublish the post.
The detail information of usage and option can be found in the [repository](https://github.com/jekyll/jekyll-compose).

Enjoy.


