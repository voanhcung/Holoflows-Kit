<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [@holoflows/kit](./kit.md) &gt; [AsyncCall](./kit.asynccall.md)

## AsyncCall variable

Async call between different context.

High level abstraction of MessageCenter.

\# Shared code - How to stringify/parse parameters/returns should be shared, defaults to NoSerialization. - `key` should be shared.

\# One side - Should provide some functions then export its type (for example, `BackgroundCalls`<!-- -->) - `const call = AsyncCall<ForegroundCalls>(backgroundCalls)` - Then you can `call` any method on `ForegroundCalls`

\# Other side - Should provide some functions then export its type (for example, `ForegroundCalls`<!-- -->) - `const call = AsyncCall<BackgroundCalls>(foregroundCalls)` - Then you can `call` any method on `BackgroundCalls`

Note: Two sides can implement the same function

<b>Signature:</b>

```typescript
AsyncCall: <OtherSideImplementedFunctions = {}>(implementation: Record<string, ((...args: any[]) => Promise<any>) & AsyncCallExecutorOptions>, options?: Partial<AsyncCallOptions>) => OtherSideImplementedFunctions
```

## Example

- Mono repo - - UI part

```ts
const UI = {
     async dialog(text: string) {
         alert(text)
     },
}
export type UI = typeof UI
const callsClient = AsyncCall<Server>(UI)
callsClient.sendMail('hello world', 'what')

```
- - On server

```ts
const Server = {
     async sendMail(text: string, to: string) {
         return true
     }
}
export type Server = typeof Server
const calls = AsyncCall<UI>(Server)
calls.dialog('hello')

```
