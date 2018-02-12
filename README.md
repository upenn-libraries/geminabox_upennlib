## README for geminabox_upennlib

This is a relatively vanilla deployment of `geminabox` using docker-compose for orchestration and the [spoonest/geminabox](https://hub.docker.com/r/spoonest/geminabox/) Docker image.

### Deployment

To deploy, configure a `.env` file with vaules for the following variables:

* `PRIVATE` - Optionally set the deployment to limit access across the board.  Valid values are `true` or `false`.  Defaults to `false`.
* `USERNAME` - Username for add/remote authentication
* `PASSWORD` - Password for add/remove authentication
* `LOCAL_GEM_STORAGE` - absolute path on the filesystem where installed gems will be stored.  This is mapped as a Docker volume.

### Publishing gems

To publish gems, first install [gemtoabox](https://github.com/yuri-karpovich/gemtoabox).  Gems can be published with the following syntax:

`gem inabox gemfile -g https://USERNAME:PASSWORD@HOSTNAME:PORT`

### Including gems

To include gems published to the gem server, include the following in your `Gemfile`:

`source 'https://HOSTNAME:PORT'`

If the gemserver is set to private, include the following in your `Gemfile`:

`source 'https://USERNAME:PASSWORD@HOST:PORT'`