# edikch
The source code of edik.ch

Google for "jekyll" if you don't know how this works. You can find a few informations and links about it on [about.md](about.md).

Some special notes:
* Set "url" and "baseurl" in _private-config.yml by yourself. This file is listed in .gitignore
* You probably don't need all configurations of my .htaccess file
* Since I'm hosting my website on a shared web hosting service, I can't enjoy the full Apache configuration power. I guess that's the reason why I can't forbid
direct access to the custom error pages without anulling the ErrorDocument directives in .htaccess. Compare the following discussions about the same problem:
https://stackoverflow.com/questions/8469041/restrict-direct-access-to-error-pages
(german) https://www.df.eu/forum/threads/49012-Zugriff-auf-ErrorDocument-403-verweigert
