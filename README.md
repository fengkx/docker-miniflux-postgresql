# docker-miniflux-postgresql
docker of miniflux RSS Reader with PostgreSQL in docker-compose

# Highlights
This docker-compose add chinese fulltext search support. 

But it do well in English or any other space splitted language.

# Usage
1. change the environment variable in `docker-compose.yml` as you need

2. run `docker-compose up -d`

enjoy it

# Notice
~~It is currently using [my fork of miniflux](https://github.com/fengkx/miniflux/tree/fork)~~

Most of the features under the hood has workaround or solution now. I switch it to the offical branch.
You can find the old docker-compose file in `docker-compose.legacy.yml`

~~ It has these features haven't been merged to miniflux master ~~

1. ~~[Regex filter for entry title and content](https://github.com/miniflux/miniflux/pull/372)~~ Miniflux has [filter rules](https://miniflux.app/docs/rules.html#filtering-rules) now.
2. ~~[Configuratble request timeout for slow network](https://github.com/miniflux/miniflux/pull/373) by setting `REQUEST_MAX_TIMEOUT` env~~
3. ~~[Mercury parser API support](https://github.com/miniflux/miniflux/issues/374)~~ Readability working good
4. ~~[font-src header for stylus](https://github.com/miniflux/miniflux/pull/392)~~ You can change the header in a reverse proxy. A caddyfile config down below
```caddyfile
rss.fengkx.top {
    encode zstd gzip
    reverse_proxy 127.0.0.1:1541
    header -content-security-policy
    header "content-security-policy" "default-src 'self'; img-src * data:; media-src *; frame-src *; font-src *;"
}
```
