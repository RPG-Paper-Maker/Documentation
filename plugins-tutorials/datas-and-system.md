---
description: The JSON files handle.
---

# Datas & System

The `Datas` folder mainly contains every `System` lists associated to a JSON file. The `System` folder contains classes in Datas lists, so it always contains a `read` function with json as parameter. Example with `System.Animation`:

```javascript
/**
 *  Read the JSON associated to the animation
 *  @param {Record<string, any>} json Json object describing the animation
 */
read(json) {
    this.pictureID = Utils.defaultValue(json.pid, 1);
    this.positionKind = Utils.defaultValue(json.pk, AnimationPositionKind
        .Middle);
    this.frames = [];
    Utils.readJSONSystemList({ list: json.f, listIDs: this.frames, cons: AnimationFrame });
    this.rows = Utils.defaultValue(json.r, 5);
    this.cols = Utils.defaultValue(json.c, 5);
}
```

{% hint style="info" %}
In **MVC \(Model View Controler\)** pattern, you can see System and Datas classes as Model one.
{% endhint %}

It will contain all the datas read from JSON files. Those files are generated thanks to RPG Paper Maker engine. The difference between `System` and `Core` classes is that System are always dependent to a JSON file.

