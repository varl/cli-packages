# Commands

A command is a plugin `module` which exports an object with two
properties: `id` and `fn`.

```
module.exports = {
    id: 'command name',
    fn: (cwd, args) => {}
}
```

The plugin is then added to the `cmds` array in `lib/cmds.js`:

```
const cmds = [
    require('./cmd/link.js'),
    require('./cmd/publish.js'),
    require('./cmd/copy.js'),
    require('./cmd/run.js'),
]
```

## `id`

This is the identifier for the command, which is also what is used from
the command line.

## `fn`

A function which receives two parameters: `cwd` and `args`.

- `cwd` is the current working directory for the script
- `args` is any other parameters which were passed from the command
  line.