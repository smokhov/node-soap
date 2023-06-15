---
"@axah/soap": patch
---

fix: change Content-Transfer-Encoding for attachements to base64


In JavaScript, using toString() on a Buffer object converts the buffer to a string using a specified encoding. If no encoding is specified, it defaults to 'utf8'.

This is potentially dangerous when dealing with binary data, because binary data doesn't necessarily represent valid UTF-8 encoded data. If you try to convert binary data to a UTF-8 string using toString(), you could end up with a string that contains invalid UTF-8 sequences. This can lead to data corruption because certain bytes may not be able to be accurately represented in a UTF-8 string.

Furthermore, when dealing with large files or data streams, converting the entire buffer to a string could cause your application to run out of memory. This is because JavaScript strings take up more memory than Buffer objects of the same size.

That's why, when working with binary data, it's usually safer to work with Buffer objects directly, or to use an encoding like 'base64' that can accurately represent any binary data in a string format. This prevents data corruption and helps ensure your application runs efficiently.

If you know for sure that your Buffer contains text data encoded with a specific encoding (like 'utf8', 'ascii', etc.), then you can use toString() with that encoding to get the string. If you don't know the encoding or if the Buffer contains non-text data, then using toString() could be problematic.
