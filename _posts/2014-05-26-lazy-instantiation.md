---
layout: post
title: TIL&#58; Lazy Instantiation
comments: true
---

I'm teaching myself Objective-C, and I recently encountered the idea of *lazy instantion*, which I thought was interesting. From [Wikipedia](http://en.wikipedia.org/wiki/Lazy_initialization), it is "the tactic of delaying the creation of an object, the calculation of a value, or some other expensive process until the first time it is needed" - it's an optimization technique. It's nothing particularly new or uncommon, but I didn't know it had a name.  

The example I was working with was something like this:

{%highlight objective-c%}

@property (strong, nonatomic) NSMutableArray *cards
...
- (NSMutableArray *)cards
{
	if(!_cards) _cards = [[NSMutableArray alloc] init];
	return _cards;
}

{% endhighlight %}

The cards property is initialized to nil (in the first line we are only creating the pointer to the object), so to actually create the object itself, we first check if it's nil, and if it is, we initialize it. This is clearly useful in situations where you may not need to initialize cards everytime, so it would be a waste of memory to unnecessarily initialize.

Other resources (in Java):  
* [Java Practices](http://www.javapractices.com/topic/TopicAction.do?Id=34)
* [Java World](http://www.javaworld.com/article/2077568/learn-java/java-tip-67--lazy-instantiation.html)