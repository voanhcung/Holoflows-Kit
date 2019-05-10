<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [@holoflows/kit](./kit.md) &gt; [LiveSelector](./kit.liveselector.md) &gt; [querySelector](./kit.liveselector.queryselector.md)

## LiveSelector.querySelector() method

Select the first element that is a descendant of node that matches selectors.

<b>Signature:</b>

```typescript
querySelector<K extends keyof HTMLElementTagNameMap>(selector: K): LiveSelector<HTMLElementTagNameMap[K]>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  selector | <code>K</code> |  |

<b>Returns:</b>

`LiveSelector<HTMLElementTagNameMap[K]>`

## Example


```ts
ls.querySelector('div#root')

```
