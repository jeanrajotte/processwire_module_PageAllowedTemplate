Page Tree Allowed Child Template
===========================

### ProcessWire Admin: New pages under are constrained to a specific template

Processwire already offers a way to constraint which template is assigned to a child page as a function of the parent page template.  However this requires the creation of template families which can clutter the template namespace.

This is a *very simple* alternative which allows to constraint the child template on a per-page basis.  

The module's admin interface is completely borrowed from PageTreeAddNewChildsReverse, repurposed.

This hasn't been super tested. And it functions rather primitively using two (2) hooks:

* On page add, the only valid template is established, so the user does not get to pick.
* On page edit, although the list of possible templates for the child page is not constrained, any change the user makes to the template is ignored. There is always a message shown to remind the user they cannot change the template, whether they tried to or not.

So, it's not slick. It feels "tacked on". But it does the job...

### How to use it

Download the module into your site/modules/ directory and install it. 

In the config page you find a single textarea field. 

Here, one family per line, you can enter the parent's page-ID, a comma, and the template name to constrain the children pages.

A few examples: 
```
1033,album
234,news-item
```
