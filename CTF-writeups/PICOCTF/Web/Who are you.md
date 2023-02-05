## Resources

[writeup]([CTFtime.org / picoCTF 2021 / Who are you / Writeup](https://ctftime.org/writeup/26905))
[docs]([HTTP headers - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers))

## Payload

```bash
curl http://mercury.picoctf.net:38322/  \
    -H "Referer: http://mercury.picoctf.net:38322/" \
    -H "Date: Thu, 11 Aug 2018 15:23:13 GMT" \
    -H "User-Agent: PicoBrowser" \
    -H "DNT: 1" \
    -H "X-Forwarded-For: 105.17.176.0" \
    -H "Accept-Language: sv, sv-fi"
```

## Flag 

picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_b22d773c}