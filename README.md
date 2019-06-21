# docker-miniflux-postgresql
docker of miniflux RSS Reader with PostgreSQL in docker-compose

# Usage
1. change the environment variable in `docker-compose.yml` as you need

2. run `docker-compose up -d`

enjoy it

# Notice
It is currently using [my fork of miniflux](https://github.com/fengkx/miniflux/tree/fork)

It has these features haven't been merged to miniflux master

1. [Regex filter for entry title and content](https://github.com/miniflux/miniflux/pull/372)
2. ~~[Configuratble request timeout for slow network](https://github.com/miniflux/miniflux/pull/373) by setting `REQUEST_MAX_TIMEOUT` env~~
3. [Mercury parser API support](https://github.com/miniflux/miniflux/issues/374)
4. [font-src header for stylus](https://github.com/miniflux/miniflux/pull/392)