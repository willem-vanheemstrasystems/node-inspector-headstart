# node-inspector-headstart
Node-Inspector - Headstart

Based on https://github.com/node-inspector/node-inspector

##Install node-inspector

Install node-inspector globally

```javascript
npm install node-inspector -g
```

##How to use

Run the following commands:

cd servers
node-debug -p {port} server.js  // where port is the port number you prefer node-inspector to run at, e.g. node-debug -p 8080 server.js

Visit http://127.0.0.1:8080/?port=5858 to start debugging.

##Debugging Gulp tasks with node-inspector

See also http://www.greg5green.com/blog/debugging-gulp-js-tasks/

Step 1) Navigate into the directory that contains the gulpfile.js from your terminal, e.g.

```javascript
cd git/myproject/
```

Step 2) Start node-inspector as follows (assuming the task 'myTask' exists in your gulpfile.js is is referenced in it)

```javascript
node-debug ($which gulp) myTask
```

NOTE: To do this on Windows, first find the full path to the gulp executable (gulp.cmd). For example, 'C:\Users\user\AppData\Roaming\npm\gulp.cmd'). Then use:

```javascript
node-debug C:\Users\user\AppData\Roaming\npm\gulp.cmd myTask
```

Step 3) The prompt will update you on the progress of node-inspector starting, then showing which port it is listening on in debug mode, e.g.:

```javascript
Node Inspector v0.12.8
Visit http://127.0.0.1:8080/?port=5858 to start debugging.
Debugging '/usr/local/bin/gulp'

Debugger listening on port 5858
```

A browser window will at the address stated above, and a breakpoint is set at the near beginning of the gulp.js file. 

Step 4) Start a gulp task (here myTask) in a separate terminal window from the directory where the gulpfile.js is, as follows:

```javascript
gulp myTask
```

Now you should be able to step through the gulpfile.js and releated files, effectively debugging the 'myTask' task.

NOTE: If no task is provided, the default task will be executed.







