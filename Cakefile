require 'shortcake'

use 'cake-test'
use 'cake-publish'
use 'cake-version'

task 'clean', 'clean project', ->
  exec 'rm -rf dist'

task 'build', 'build project', ->
  handroll = require 'handroll'

  bundle = yield handroll.bundle
    entry: 'src/index.coffee'

  yield bundle.write format: 'cjs'
  yield bundle.write format: 'es'
