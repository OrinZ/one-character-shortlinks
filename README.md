# One!!!!1!1!! Character Shortlinks

(If you're reading this and it's the current version, I'm afraid you're a bit early. I'm in the process of developing the first working implementation. Come back in a bit!)

## Description
Wordpress plugin enabling every location on your site to be accessed from the shortest possible URL: a single re-assignable character.

As of Unicode 13.0 in 2020, that provides a possible 143,732 unique characters in 154 scripts, including emoji
🤯✍🔣🎨💥🎩🏆💕

Features include:
* assign symbols automatically, choose from categories, or specify per link
* use your own domain and retain control of changes, appearance, and stats
* shortlinks are canonical, so they are easily found when sharing a page


## Installation
1. Upload the "one-character-shortlinks" folder and its contents to your "/wp-content/plugins/" directory.
1. Activate the plugin through the 'Plugins' page of your WordPress admin.
1. The plugin will automatically assign single-character shortlinks and replace the default wp.me implementation. Old wp.me links still function.
1. Access the configuration settings under the Wordpress admin's 'Posts' menu.


## Frequently Asked Questions
### Why are some characters unavailable?
For both performance reasons and perceived lack of interest, Unicode's first 127 characters (the uppercase and lowercase Latin alphabet, numbers, ASCII punctuation) are excluded. They are also more likely to interfere with existing redirection rules.

### Why can't I use ______ character set?
Look on the plugin's configuration page (located in your Wordpress admin panel within the 'Posts' menu) and you can enable many more sets which are disabled by default. As noted above, only basic ASCII is unusable. Unicode includes even ancient scripts such as "Linear A" from ancient Crete, which remains undeciphered after thousands of years.

### It's only one character, but it's being counted as two!
Unicode's first 65,536‬ characters (2^16) are stored using only two bytes. The remaining characters must use 4 bytes, which indeed often *count* as two. If you think this could be a problem, 4 byte characters can be disabled on the plugin's configuration page in your Wordpress admin (within the 'Posts' menu). However, be assured: they are not actually two characters!

### The shortcode appears to have placeholder characters like � or □ in it. What's going on?
A tricky consequence of varying systems, browsers, fonts, etc. The underlying information is preserved, this is merely a problem of displaying the correct symbols. However, it will probably be encountered only with fairly uncommon scripts (which are disabled by default) or outdated browsers. This should also improve in the future as Unicode implementation becomes more universal.

### When I copy/paste the shortlink code, why is it replaced with numbers & percentage signs?
This is the internal representation which the browser requests from your web server, usually called "URL encoding" or "percent-encoding" (%20, %3F, %u1234 for example). It won't generally be shown in modern browsers, but could be what you get if you copy the URL from the address bar. Try copying from another source on your site (or decoding it with a quick search).

### Are there drawbacks to using Unicode links I should consider?
Perhaps one which should be obvious is that users might not know how to speak or input links which are abstract symbols &mdash; especially unfamiliar ones. This can be mitigated by providing good link copying options, and by selecting only certain character sets (emoji should be relatively safe). As mentioned above, there is also the confusion of empty characters (�□) or percent-encoding (%20, %3F, %u1234). There's a slim chance a user could even fail to recognize your link *as a link* because "it looked weird!" In fairness to Unicode, this can be understood as a prototypical example of a [PEBKAC](https://www.computerhope.com/jargon/p/pebkac.htm)-type situation.

### Instead of redirecting, can the single character simply be the URL?
For this senario, the best case would probably be to use Wordpress' built-in permalink field, found on a post/page/media's edit page.

### Can I use this to link to websites besides my own?
Theoretically yes, and full implementation is planned for a future release.

### Can usage statistics be tracked?
Well no &mdash; but actually yes. While it doesn't save such data itself, it was also designed not to interfere with existing solutions for tracking stats. If you do encounter trouble please add some details on the [issue tracker](https://github.com/OrinZ/one-character-shortlinks/issues).

### Could this potentially allow phishing or other deception by using characters which look similar?
Known as "punycode" attacks, these URL hacks can indeed be quite problematic. The additional risk here should be very low, as custom shortlinks can only be added by admins or other users with sufficient editing priviledges &mdash; users who can already change permalinks. Also, it only functions on one's own website. **And** it cannot modify a domain name at all.

### Can the type of redirect (301, 302, 308) be altered?
Not yet, but planned for a future version.

### Can I draw a symbol I want to find characters in Unicode?
A very snazzy idea, which could find its way into an update one day (especially if someone familiar with that technique contributes their skill).

### How about *two* character shortlinks?
Unlikely, as the current amount of characters ought to be plenty. However, if you feel so moved for whatever reason, such as after hitting the 143,732 character limit (wow, really?) feel free to reprogram the plugin as you see fit. The LGPL software license allows free modification (and even inclusion in closed-source applications). It would be most kind to also share your changes to [this development repo](https://github.com/OrinZ/one-character-shortlinks/), not to mention intriguing to check out your HECKIN' LARGE site. No clue what the plugin would be renamed, though.

### I have a (big or little) idea for a neat improvement!
Splendid! Suggestions are quite welcome, as feedback from the folks who get something out of this plugin is the primary motivation for making it. File something in the [issue tracker](https://github.com/OrinZ/one-character-shortlinks/issues), or contribute to the [wiki](https://github.com/OrinZ/one-character-shortlinks/wiki).

### There are 1's mixed into the !'s of the plugin name... why!?
I was excited to make it, I suppose (!). You can consult [Know Your Meme: The "!1" Phenomenon](https://knowyourmeme.com/memes/the-1-phenomenon "Article explaining the phenomenon") for further info.