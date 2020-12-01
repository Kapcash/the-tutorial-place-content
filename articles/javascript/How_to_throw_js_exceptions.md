---
title: How to throw exceptions in javascript
author: Kapcash
thumbnail: 
stackoverflow:
  - https://stackoverflow.com/questions/64622145/how-to-find-the-first-and-last-values-of-an-if-statement-in-swift
  - https://stackoverflow.com/questions/64622511/flutter-firebase-query-does-not-return-link-to-auto-generate-query
  - https://stackoverflow.com/questions/64622044/how-to-implement-a-type-safe-generic-setter
---

## What are exceptions?
They are runtime errors thrown to tell the process something wrong happened.

They goes up throught all the call stack (i.e. the calling method, and its calling method, up to the main function)
but they can be catch up during they ascending by `try / catch` statements.

## What does it look like?

### Maybe like this

Maecenas scelerisque pretium nunc, a varius felis. Pellentesque sit amet nunc ipsum. In vehicula nisi mattis nulla facilisis eleifend. Quisque sollicitudin magna nec nunc blandit, et rutrum massa laoreet. Nunc porttitor ex mi, at cursus felis aliquet sit amet. Etiam ut arcu auctor, vehicula tortor eget, consequat massa. Maecenas sit amet scelerisque diam, sit amet cursus lectus. Morbi nec sapien leo. Aenean lorem dolor, condimentum ut tortor quis, tempus efficitur turpis. Fusce malesuada ut urna sit amet bibendum. Aliquam eleifend placerat nulla vitae vestibulum. Quisque in justo a mauris cursus ullamcorper. Sed vitae ex urna.

### Or like that

Like this.

```typescript
export class ChannelError extends Error {
  channelId: string;

  /**
   * @param channelId The channel id
   * @param msg [Optional] The exception message
   */
  constructor(channelId: string, msg?: string) {
    super(msg);
    Object.setPrototypeOf(this, ChannelError.prototype);

    this.channelId = channelId;
    this.message = msg || `The channel '${channelId}' have received an error!`;
  }
}
```

------------

## Basic exception

Nam convallis dapibus tellus vel efficitur. In at vulputate mauris, id cursus enim. Nullam eget gravida turpis. Sed dictum quam felis, ut suscipit est rhoncus eget. Cras sagittis lacinia est eu placerat. Maecenas luctus sodales interdum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec sed pretium metus. Duis vitae venenatis magna. Cras vehicula, nisi id luctus placerat, enim arcu congue eros, nec volutpat nibh augue sed augue.

## Custom exceptions

```typescript
export class ChannelError extends Error {
  channelId: string;

  /**
   * @param channelId The channel id
   * @param msg [Optional] The exception message
   */
  constructor(channelId: string, msg?: string) {
    super(msg);
    Object.setPrototypeOf(this, ChannelError.prototype);

    this.channelId = channelId;
    this.message = msg || `The channel '${channelId}' have received an error!`;
  }
}
```

Duis ullamcorper eleifend quam, a lacinia mauris ultrices sed. Pellentesque ullamcorper, quam id luctus feugiat, ipsum nibh tempor turpis, at finibus lectus eros a erat. Cras id odio gravida, blandit nunc convallis, rhoncus odio. Sed feugiat leo augue, a faucibus odio tincidunt et. Proin porta consequat elit, ut tempor magna maximus sed. Morbi vel efficitur lacus, non lacinia urna. Nulla et venenatis ipsum, id porttitor enim. Curabitur mattis, massa vel commodo tempus, lectus enim porttitor nibh, at congue arcu eros at sapien. Vivamus at nibh eu erat fringilla molestie et vitae urna. Sed viverra at quam quis rhoncus. Aenean at ligula feugiat, aliquam tortor eleifend, pharetra sapien.
