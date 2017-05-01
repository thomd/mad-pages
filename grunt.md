
# grunt(1)

Install

    npm i -g grunt-cli
    npm i -D grunt

Usage

    grunt -h                                           # list available tasks
    grunt --no-write                                   # disable writing files (dry run)
    grunt -v                                           # verbose mode 
    grunt \<task>                                       # run a task (runs implicitly all targets)
    grunt \<task>:\<target>                              # run a target

## gruntfile.js

    module.exports = function(grunt) {

      grunt.registerTask('test', function() {          # Basic Task
        grunt.log.write(this.name)
      })
      
      grunt.registerTask('default', ['test'])          # Alias Task
      
      grunt.initConfig({                               # Config for Multi Task
        task: {
          target: {
          
          }
        }
      })
      grunt.registerMultiTask('taskName', function() {
        grunt.log.writeln('%s: %s = %s', this.name, this.target, this.data)
      })

      grunt.task.loadNpmTasks(pluginName)              # load "pluginName" module
    }

## Best Practices

Automatically Load Tasks

    npm install -D load-grunt-tasks

    require('load-grunt-tasks')(grunt)                 # load grunt tasks matching ['grunt-\*', '@\*/grunt-*']
