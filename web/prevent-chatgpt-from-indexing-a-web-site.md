# Prevent ChatGPT From Indexing A Web Site

__Category: Web__

OpenAI have stated that the ChatGPT web crawler bot will be identifiable by the token `GPTBot` with the full user agent string of `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.0; +https://openai.com/gptbot)`

To prevent ChatGPT from indexing all of a web site, add the following to `robots.txt`:

```text
User-agent: GPTBot
Disallow: /
```

To restrict GPTBot from indexing parts of a web site, add the following to `robots.txt`:

```text
User-agent: GPTBot
Allow: /directory-1/
Disallow: /directory-2/
```
