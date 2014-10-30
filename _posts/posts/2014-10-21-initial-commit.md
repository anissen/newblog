---
layout: article
title: "Initial commit"
modified:
categories: posts
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2014-10-21T22:31:23+02:00
---

{% highlight bash %}
git add new.blog
git commit -m "Initial commit"
git push
{% endhighlight %}

{% highlight haxe %}
package examples;
import luxe.Visual;
import phoenix.Texture;

/**
 * ...
 * @author Josu Igoa
 */
class ImageExample
{
    var visual:Visual;
    var image:Texture;
    
    public function new() 
    {
        //load the image
        image = Luxe.loadTexture('assets/luxe.png');
        //tell us once the image is loaded by
        //calling the create_player function
        image.onload = texture_loaded;
    }
    
    function texture_loaded(_)
    {
        //now that the image is loaded
        //keep pixels crisp when we resize it
        image.filter = FilterType.nearest;
        
        //work out the correct size based on a ratio
        var h = Luxe.screen.h * .2;
        var w = (h / image.height) * image.width;
        
        visual = new Visual( {
            name:"irudia",
            texture: image,
            pos:Luxe.screen.mid,
            size:new Vector(w, h)
        });
    }
    
}
{% endhighlight %}

This is the start of my new blog. This is the initial commit and lots more will follow.
