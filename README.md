# Open Distro for Elasticsearch Alerting Kibana

The Open Distro for Elasticsearch alerting Kibana plugin lets you manage your [Open Distro for Elasticsearch alerting plugin](https://github.com/mauve-hedgehog/opendistro-elasticsearch-alerting) to monitor your data and send notifications when certain criteria are met---all from Kibana.


# Highlights

- Create and schedule *monitors*, which run period queries against data in Elasticsearch.
- Evaluate query results against *triggers* to see if they meet certain criteria.
- If trigger criteria are met, generate *alerts* and perform *actions* (e.g. post a message in a Slack channel).


# Technical Documentation

Please see our [technical documentation](https://opendistro.github.io/for-elasticsearch-docs/).


# Developer setup, build, and run


## Setup

1. Download Elasticsearch for the version that matches the [Kibana version specified in package.json](./package.json#L9).
1. Download and install the appropriate [Open Distro for Elasticsearch Alerting plugin](https://github.com/mauve-hedgehog/opendistro-elasticsearch-alerting).
1. Download the Kibana source code for the [version specified in package.json](./package.json#L9) you want to set up.

   See the [Kibana contributing guide](https://github.com/elastic/kibana/blob/master/CONTRIBUTING.md) for more instructions on setting up your development environment.
   
1. Change your node version to the version specified in `.node-version` inside the Kibana root directory.
1. Create a `kibana-extra` directory as a sibling directory to the Kibana source code directory.
1. Check out this package from version control into the `kibana-extra` directory.
1. Run `yarn kbn bootstrap` inside `kibana-extra/opendistro-elasticsearch-alerting-kibana`.

Ultimately, your directory structure should look like this:

```md
.
├── kibana
├── kibana-extra
│   └── opendistro-elasticsearch-alerting-kibana
```


## Build

To build the plugin's distributable zip simply run `yarn build`.

Example output: `./build/opendistro-alerting-0.7.0.0.zip`


## Run

- `yarn start`

  Starts Kibana and includes this plugin. Kibana will be available on `localhost:5601`.

- `NODE_PATH=../../kibana/node_modules yarn test:jest`

  Runs the plugin tests.


# Contributing to Open Distro for Elasticsearch Alerting Kibana

- Refer to [CONTRIBUTING.md](./CONTRIBUTING.md).
- Since this is a Kibana plugin, it can be useful to review the [Kibana contributing guide](https://github.com/elastic/kibana/blob/master/CONTRIBUTING.md) alongside the documentation around [Kibana plugins](https://www.elastic.co/guide/en/kibana/master/kibana-plugins.html) and [plugin development](https://www.elastic.co/guide/en/kibana/master/plugin-development.html).


# License

This code is licensed under the [Apache License, Version 2.0](https://github.com/mauve-hedgehog/opendistro-elasticsearch-alerting/blob/master/LICENSE.txt).