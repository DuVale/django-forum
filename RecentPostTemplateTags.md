# Introduction #

To tie your forums into your web page even more, it can be useful to show the most recent forum threads on your homepage or in your sidebar. Some 'Template Tags' are provided to do just that.


# Usage #

In your homepage template, near the top of the page add the line:

```
{% load forum_tags %}
```

## Most Recent Posts ##

Where you want to display the most recent POSTS, insert the following code. This may include multiple posts for a single thread.

```
{% forum_latest_posts 5 as latest_posts %}
<ul>
{% for post in latest_posts %}
<li><strong><a href='{{ post.get_absolute_url }}'>{{ post.title }}</a></strong> {{ post.latest_post_time|timesince }} ago</li>
{% endfor %}
</ul>
```

## Recent Threads With Activity ##

Alternatively you can display THREADS with recent activity, so each thread is only listed once:

```
{% forum_latest_thread_activity 5 as latest_activity %}
<ul>
{% for post in latest_activity %}
<li><strong><a href='{{ post.get_absolute_url }}'>{{ post.title }}</a></strong> {{ post.latest_post_time|timesince }} ago</li>
{% endfor %}
</ul>
```

## Recent posts for a user ##

You can display recent posts for a user by providing their username to the relevant function:

```
{% forum_latest_user_posts user.username 5 as latest_posts %}
{% for post in latest_posts %}
<li><strong><a href='{{ post.get_absolute_url }}'>{{ post.title }}</a></strong> {{ post.latest_post_time|timesince }} ago</li>
{% endfor %}
```

Note that you must always provide the **username** to this templatetag, not a user object.