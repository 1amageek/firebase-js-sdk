Project: /docs/reference/js/_project.yaml
Book: /docs/reference/_book.yaml
page_type: reference

{% comment %}
DO NOT EDIT THIS FILE!
This is generated by the JS SDK team, and any local changes will be
overwritten. Changes should be made in the source code at
https://github.com/firebase/firebase-js-sdk
{% endcomment %}

# LoadBundleTask class
Represents the task of loading a Firestore bundle. It provides progress of bundle loading, as well as task completion and error events.

The API is compatible with `Promise<LoadBundleTaskProgress>`<!-- -->.

<b>Signature:</b>

```typescript
export declare class LoadBundleTask implements PromiseLike<LoadBundleTaskProgress> 
```
<b>Implements:</b> PromiseLike&lt;[LoadBundleTaskProgress](./firestore_.loadbundletaskprogress.md#loadbundletaskprogress_interface)<!-- -->&gt;

## Methods

|  Method | Modifiers | Description |
|  --- | --- | --- |
|  [catch(onRejected)](./firestore_.loadbundletask.md#loadbundletaskcatch) |  | Implements the <code>Promise&lt;LoadBundleTaskProgress&gt;.catch</code> interface. |
|  [onProgress(next, error, complete)](./firestore_.loadbundletask.md#loadbundletaskonprogress) |  | Registers functions to listen to bundle loading progress events. |
|  [then(onFulfilled, onRejected)](./firestore_.loadbundletask.md#loadbundletaskthen) |  | Implements the <code>Promise&lt;LoadBundleTaskProgress&gt;.then</code> interface. |

## LoadBundleTask.catch()

Implements the `Promise<LoadBundleTaskProgress>.catch` interface.

<b>Signature:</b>

```typescript
catch<R>(onRejected: (a: Error) => R | PromiseLike<R>): Promise<R | LoadBundleTaskProgress>;
```

### Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  onRejected | (a: Error) =&gt; R \| PromiseLike&lt;R&gt; | Called when an error occurs during bundle loading. |

<b>Returns:</b>

Promise&lt;R \| [LoadBundleTaskProgress](./firestore_.loadbundletaskprogress.md#loadbundletaskprogress_interface)<!-- -->&gt;

## LoadBundleTask.onProgress()

Registers functions to listen to bundle loading progress events.

<b>Signature:</b>

```typescript
onProgress(next?: (progress: LoadBundleTaskProgress) => unknown, error?: (err: Error) => unknown, complete?: () => void): void;
```

### Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  next | (progress: [LoadBundleTaskProgress](./firestore_.loadbundletaskprogress.md#loadbundletaskprogress_interface)<!-- -->) =&gt; unknown | Called when there is a progress update from bundle loading. Typically <code>next</code> calls occur each time a Firestore document is loaded from the bundle. |
|  error | (err: Error) =&gt; unknown | Called when an error occurs during bundle loading. The task aborts after reporting the error, and there should be no more updates after this. |
|  complete | () =&gt; void | Called when the loading task is complete. |

<b>Returns:</b>

void

## LoadBundleTask.then()

Implements the `Promise<LoadBundleTaskProgress>.then` interface.

<b>Signature:</b>

```typescript
then<T, R>(onFulfilled?: (a: LoadBundleTaskProgress) => T | PromiseLike<T>, onRejected?: (a: Error) => R | PromiseLike<R>): Promise<T | R>;
```

### Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  onFulfilled | (a: [LoadBundleTaskProgress](./firestore_.loadbundletaskprogress.md#loadbundletaskprogress_interface)<!-- -->) =&gt; T \| PromiseLike&lt;T&gt; | Called on the completion of the loading task with a final <code>LoadBundleTaskProgress</code> update. The update will always have its <code>taskState</code> set to <code>&quot;Success&quot;</code>. |
|  onRejected | (a: Error) =&gt; R \| PromiseLike&lt;R&gt; | Called when an error occurs during bundle loading. |

<b>Returns:</b>

Promise&lt;T \| R&gt;
