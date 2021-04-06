# @dexare/logger
A [Dexare](https://github.com/Dexare/Dexare) module for colorful logging with [winston](https://npm.im/winston) and [chalk](https://npm.im/chalk).

```sh
npm install @dexare/logger
```

```js
const { DexareClient } = require('dexare');
const LoggerModule = require('@dexare/logger');

const config = {
  // All props in this config are optional, defaults are shown unless told otherwise
  logger: {
    // The level to log at, defaults to 'info' if process.env.NODE_ENV is 'production'
    level: 'debug',
    // The options object for util.inspect
    inspectOptions: {}
  }
}

const client = new DexareClient(config);
client.loadModules(LoggerModule);
// ...

// You can set the color of a module or level by defining it
// in `module.moduleColors` and `module.levelColors` respectively
const chalk = require('chalk');
const logger = client.modules.get('logger');
logger.moduleColors.info = chalk.black.bgCyan;

// Loggers are also created per module in `winston.loggers`.
```
