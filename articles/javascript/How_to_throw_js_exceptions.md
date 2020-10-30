---
title: How to throw exceptions in javascript
author: Kapcash
thumbnail: 
---

## What are exceptions?
They are runtime errors thrown to tell the process something wrong happened.

They goes up throught all the call stack (i.e. the calling method, and its calling method, up to the main function)
but they can be catch up during they ascending by `try / catch` statements.

## What does it look like?

Like this.

------------

## Basic exception

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
