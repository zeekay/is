use 'sake-bundle'
use 'sake-outdated'
use 'sake-publish'
use 'sake-version'

task 'clean', 'clean project', ->
  exec 'rm -rf lib'

task 'build', 'build project', ->
  yield exec 'coffee -bcm -o ./ src/'
  yield exec 'mv index.js index.mjs'
  yield bundle.write
    entry:  'src/cjs.coffee'
    dest:   'index.js'
    format: 'cjs'

task 'test', 'test project', ['build'], ->
  require './test'

task 'test2', 'test project', ['build'], ->
  bundle.write
    entry:  'test.js'
    dest:   'bundle.js'
    format: 'es'
    external: false
