---
title: The best ways to work with yaml files in Emacs
author: chmouel
date: 2016-09-07T07:45:03+00:00
url: /2016/09/07/dealing-with-yaml-in-emacs/
tags:
  - Emacs
  - OpenShift
  - Programming

---
Sometime ago or at least when I started doing programming in the late 90s **XML** was all the rage, it promised to be the panacea for everything from data to storage to data presentation and processing. People [realized][1] that it was just complexity as Joel Spolski points out _an attempt to make the complex seem accessible to ordinary people._. Really people were annoyed to write all those tags as those '<' and '>' are hard to reach on a qwerty keyboard.

Beginning the new millennia in 2000 the web started to get very popular and things like "web services" popped up everywhere, people realised that actually XML is not that great so started to get a format called **Json** to get computers talking to each others in a sane manner.

But people realise that json was actually not that great to chat between web services as it was actually designed to serialize objects between programming languages. And really down the line it's more about the programmers being annoyed by all those { } [ ] brackets

So here came yaml the latest "fashion format" based on the popularity of tab based programming languages.

Most new software lately have been using it, all the containers software ecosystem configure things in yaml so you have to deal with it when you work with them.

I don't know if I like yaml or not, the only thing i know is that when I have a big ass large yaml file it become quickly unreadable. You have no idea which blocks belong to which one and not sure how many indents you need to add to that block to align to that other one that started 800 lines ago.

This has been driving me crazy as I need to write some large kubernetes/OpenShift yaml files and sometime end up for hours trying to detect where I have my tab alignment.

Some may argue, _but you do python and python is tab based_. Yeah i have been doing python for the last 10 years and this has never been issue cause first I don't write kick ass 5000 lines python functions and second the python mode of my editor Emacs is properly configured.

Ah there I say it, the editor needs to be configured properly to have a good workflow so here is Emacs to the rescue to make it bearable (and make that post more productive that another rant from the interweb)

So without further ado and with much fanfare, here is the emacs extension i found to make writing yaml bearable :

[Highlight Indentation for Emacs][2]

![/wp-content/uploads/2016/09/2016-09-07__09-06-21-543.png][3]

This mode would give you a visual representation of the current indentation with a bar showing the indentation.

[Smart Shift][4]

![](/wp-content/uploads/2016/09/t.gif)

This mode doesn't give you a visual but allow you to indent blocks of texts easily. Usually in emacs you would use the Control-x Tab command to indent and prefix it with a number for the number of indent. For example C-u 4 Control-x Tab would indent the text for 4 spaces. Smart shift make things much easier to move around.

[Flycheck-mode][6]

![/wp-content/uploads/2016/09/2016-09-07__09-24-14-5881.png][7]

This is a generics mode you should really configure for all your programming needs, it supports yaml files and will try to validate (with ruby-yaml library) your yaml file and see where you have an error.

[aj-toggle-fold][8]

![/wp-content/uploads/2016/09/2016-09-07__09-36-55-32078.png][9]

This is a function I found in a post on stackoverflow (by the author of Highlight-Indentation-for-Emacs) it allow you to folds all code on an indentation level greater than the current line. A great way to show you the current outline of the file.

 [1]: http://discuss.fogcreek.com/joelonsoftware/default.asp?cmd=show&ixPost=953
 [2]: https://github.com/antonj/Highlight-Indentation-for-Emacs
 [3]: /wp-content/uploads/2016/09/2016-09-07__09-06-21-543.png
 [4]: https://github.com/hbin/smart-shift
 [5]: /wp-content/uploads/2016/09/t.gif
 [6]: http://flycheck.org
 [7]: /wp-content/uploads/2016/09/2016-09-07__09-24-14-5881.png
 [8]: https://stackoverflow.com/questions/1587972/how-to-display-indentation-guides-in-emacs/4459159#4459159
 [9]: /wp-content/uploads/2016/09/2016-09-07__09-36-55-32078.png
