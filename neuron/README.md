# Neuron

[Neuron](https://neuron.zettel.page) is a zettelkasten notetaking system.

## Limitations of using Neuron with Whalebrew

### Use as a transform tool; `neuron open` and editing functions don't work

The primary usage of Neuron from Whalebrew is to serve from an existing
Neuron notes directory. As such, `neuron open` doesn't work because
Neuron uses `open` or `xdg-open`, and these do not exist within the container
and cannot be passed back to the host for operation. Also,
`neuron search --edit` won't work because the container does not ship editors.

You may be able to work around this with a script that wraps the Whalebrew
launcher.

### Ports 8080 and 1440 are only serving ports

Whalebrew as of 0.2.5 cannot dynamically change exposed ports, so this exposes
ports 8080 and 1440. The latter is available in case you already have something
running on 8080.

Use `-s 0.0.0.0:8080` or `:1440`  when invoking `neuron rib` when you want to
use Rib's built-in server from within the container.


