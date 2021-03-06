# Searching Messages
## Introduction

Rocket Chat search supports basic search commands which work similar to Gmail search.

Rocket Chat also supports the use of "[regular expressions](https://en.wikipedia.org/wiki/Regular_expression)", the benefits of which are great search flexibility and the ability to search chat entries in any language, even ones which are traditionally a challenge for search (e.g. "CJK" languages - Chinese, Japanese, Korean). 

## Basic Search Commands

You can use the following commands before or after entering your search term:

`from:me` to search for messages only created by the current user.

`from:user.name` to search for messages created by a specific user. The username entered must be the format without spaces (i.e. "john.doe" and not "John Doe". If you want to search for anytime a user was mentioned, simply search for their username.

`has:star` returns messages that are starred by the current user.

`is:pinned` or `has:pin` returns messages that are pinned in the current channel.

`has:url` or `has:link` returns messages that contain a link.

`has:location` or `has:map` returns messages that have a location attached

`before:dd/mm/yyyy`, `after:dd/mm/yyyy` and `on:dd/mm/yyyy` return message that were created before, after or on the provided date.
You can also use dashes `dd-mm-yyyy` or dots `dd.mm.yyyy` instead of slashes.

`order:asc` sorts messages by ascending timestamp. You can also use `order:ascend` or `order:ascending`

`order:desc` sorts messages by ascending timestamp. You can also use `order:descend` or `order:descending`.

## Basic Regex Examples

Regular expressions are a deep, but admittedly geeky topic. The flexibility of "regex" search increases as you learn more about how to write regex patterns, but if you learn just a couple of simple patterns, you can benefit right away. 

Let's see a few simple examples that you can try. 

### "Bare" word search
You can simply enter a search term in the search box and press enter. This works in many cases, but not for CJK-type languages. 

### Find the capitalized string "BTW"

Enter `/BTW/` to find the capitalized variant of a search string. The slashes `//` bookend the string, and tell the system "this is a regex pattern".  

### Find a CJK string

Enter a CJK language string between slashes, like `/ブラジル連邦共和国/` (Japanese for República Federativa do Brasil), and Rocket Chat search will return posts with that string. 

> _N.b._ - CJK users should be careful to use standard ASCII slashes, and not any unicode variants. That is, `/` but not a double-byte `／`, as the latter will not work.

### Find "BTW" or "btw"

Enter `/BTW/i` with a trailing "i", meaning "ignore case". Actually, it works for "Btw" or "bTw" etc, too.

### Find "BTW" in specific positions

Enter `/^BTW/i` to find posts with "BTW" or "btw" anchored to the beginning of the post. The `^` is the start anchor.

Enter `/BTW$/i` to find posts with "BTW" or "btw" anchored to the end of the post. The `$` is the end anchor. 

### Find word variants

Enter `/^Any(body|one)/i` to find posts that start with "Anybody" or "Anyone". The `(body|one)` bit means to find "body" or "one".

Enter `/(nginx|apache)/i` to find posts with either "nginx" or "apache".

Enter `/(東京|京都)/i` to find posts with either "Tokyo" or "Kyoto".

### Find a string surrounded by spaces

Enter `/\s+123456\s+/i` to find " 123456 " with a space before and after.

## Conclusion

Those are enough examples to get you started. If you're interested, please use the following references to learn more about the deep world of regex. 

### Reference

* Wikipedia - https://en.wikipedia.org/wiki/Regular_expression
* Regex 101 - https://regex101.com/#javascript
* Regexr - http://regexr.com/
* Regex Info - http://www.regular-expressions.info/javascriptexample.html


