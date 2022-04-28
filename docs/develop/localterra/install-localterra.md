# Install LocalTerra

## Prerequisites

- [Docker](https://www.docker.com/)
- [`docker-compose`](https://github.com/docker/compose)
- At least 16 GB of RAM
- [Terra Station Chrome extension](../../../learn/terra-station/download/terra-station-extension.md)
- Node.js version 16

:::{admonition} Node version error
:class: warning
Use LTS Node.js 16 if you encounter the following error code:  
`error:0308010C:digital envelope routines::unsupported`
:::

(header_target)=
:::{dropdown} Running NPM on M1 Macs

Some M1 macs may need to use the latest LTS version of Node to complete this tutorial. Consider using a node version manager such as [NVM](https://github.com/nvm-sh/nvm/blob/master/README.md). 
After installing NVM, run the following to install and use the latest LTS version of node:

```sh
nvm install --lts
nvm use --lts
```

The `nvm use --lts` command will need to be run every time you open a new terminal to use the LTS version of node. 

To default to the LTS version of node when restarting your terminal, run the following:

```sh
nvm alias default <INSERT NODE VERSION HERE>
```
:::

## Install and run LocalTerra

1. To download LocalTerra, run the following commands:

   ```sh
   git clone --branch v0.5.2 --depth 1 https://github.com/terra-money/localterra
   ```

2. Start LocalTerra by running the following:

   ```sh
   cd localterra
   docker-compose up
   ```

:::{admonition} Docker error: increase memory
:class: danger

If you encounter an error with LocalTerra, you may need to increase your Docker resources. Click on the Docker icon, then click **Preferences**. In the Preferences window, click **Resources**. Increase the memory slider and restart LocalTerra. Repeat as needed. 

:::

3. You will start seeing LocalTerra block activity in your terminal.

:::{admonition} LocalTerra Accounts
:class: note
To view the LocalTerra wallet information, visit the [LocalTerra accounts page](../../how-to/localterra/accounts.md). 
For more configuration options, visit the [LocalTerra configuration page](../../how-to/localterra/configure.md). 
:::


### Start

```sh
$ docker-compose up
```

Your environment now contains:

- [terrad](http://github.com/terra-money/core) RPC node running on `tcp://localhost:26657`
- LCD running on http://localhost:1317
- [FCD](http://www.github.com/terra-money/fcd) running on http://localhost:3060
- An oracle feeder feeding live prices from mainnet, trailing by one vote period

### Stop

```sh
$ docker-compose stop
```

### Reset

```sh
$ docker-compose rm
```
