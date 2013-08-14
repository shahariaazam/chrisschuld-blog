---
title: Format PHP Formatting User IO
layout: single-sidebar
pagesl: 2
isChild: true
include: true
---

####Format.php – Formatting User I/O

Format.php is a class used statically to formation information to and from the user. Right now the class is fairly US based because that is where most of my applications are from. If you would like to help update some of the functions to have better international support please let me know.

Here are some of the functions that Format.php provides&#58;

**Phone Number Formatting:** (ZZZ) ZZZ-ZZZZ x YYY
**Phone Number Formatting for Storage:** numbers only
*Please Note: In all of my applications I usually do not store the phone numbers as the users enter them but rather format them into something the application can use and understand (I pack them and un-pack them with known heuristics).*

**USD:** USA dollar format: $0000.00
**Bytes:** format a number given as bytes into a readable format such as 32MB
**KiloBytes:** format a number give as kilobytes into a readable format such as 23GB

Here is some typical usage&#58;

{% highlight php %}
echo Format::phoneNumberForStorage('480-373-6581').'
';
echo Format::phoneNumberForStorage('373-6581').'
';
echo Format::phoneNumber(Format::phoneNumberForStorage('800-959-0045')).'
';
echo Format::phoneNumber('3736581').'
';
echo Format::phoneNumber('3736581','480').'
';
echo Format::usd(56.32).'
';
echo Format::bytes(20375237).'
';
echo Format::kilobytes(20375237).'
';
{% endhighlight %}

[This typical usage will output this&#58;](#typicalusage)

`4803736581
3736581
(800) 959-0045
373-6581
(480) 373-6581
$56.32
19.43 MB
19.43 GB`