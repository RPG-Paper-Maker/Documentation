---
description: Event commands handling.
---

# Event commands

The folder `EventCommand` contains every Event command class. Those classes are interpreted thanks to `Core.ReactionInterpreter`. The Manager.Events will be the one sending events to objects. Then, when receiving the event, the object will instanciate a new `Core.ReactionInterpreter`.

An `EventCommand` class will contain these methods:

```javascript
initialize() {
    return null;
}

update(currentState, object, state) {
    return 1;
}

onKeyPressed(currentState, key) {
}

onKeyReleased(currentState, key) {
}

onKeyPressedRepeat(currentState, key) {
    return true;
}

onKeyPressedAndRepeat(currentState, key) {
    return true;
}

drawHUD(currentState) {
}
```

The `initialize` method is the Object that will be named `currentState` in the other methods parameters. In the update method, you need to return the number of node that will be added to the current node position in the reaction. So if you return 0, you won't move and keep updating this command. If you return 1, you'll go to the next command after the current one.

