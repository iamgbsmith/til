# Get Weather Information From The Command Line

__Category: Linux__

You can get weather information from the command line using `curl` from the site https://wttr.in

For example, the following will obtain weather for New York:

```shell
curl wttr.in/"New York"
```

Obtain weather for three different locations at once using short format:

```shell
curl -s "wttr.in/{Auckland,Wellington,Christchurch}?format=3"
```

Output:

```shell
Auckland: ⛅️  +11°C
Wellington: ⛅️  +9°C
Christchurch: ☀️ +3°C
```

If you omit the location you will get the report for your current location based on your IP address.

See [chubin/wttr.in](https://github.com/chubin/wttr.in) for more details.
