---
id: useMutationObserverRef
title: useMutationObserverRef
sidebar_label: useMutationObserverRef
---

## About

A hook that tracks mutations of an element. It returns a callbackRef.

## Installation

    npm install --save rooks

## Importing the hook

```javascript
import { useMutationObserverRef } from "rooks";
```

## Usage

```jsx
function Demo() {
  const [mutationCount, setMutationCount] = useState(0);
  const incrementMutationCount = () => {
    return setMutationCount(mutationCount + 1);
  };
  const [myRef] = useMutationObserverRef(incrementMutationCount);
  const [XOffset, setXOffset] = useState(0);
  const [YOffset, setYOffset] = useState(300);
  return (
    <>
      <div
        style={{
          width: "auto",
          background: "lightblue",
          padding: "10px",
          position: "absolute",
          left: XOffset,
          top: YOffset,
        }}
        ref={myRef}
      >
        <div
          style={{
            resize: "both",
            overflow: "auto",
            background: "white",
            color: "blue",
            maxWidth: "100%",
          }}
        >
          <p>
            Resize this div as you see fit. To demonstrate that it also updates
            on child dom nodes resize
          </p>
        </div>
        <h2>Bounds</h2>
        <p>
          <button onClick={() => setXOffset(XOffset - 5)}> Move Left </button>
          <button onClick={() => setXOffset(XOffset + 5)}> Move Right </button>
        </p>
        <p>
          <button onClick={() => setYOffset(YOffset - 5)}> Move Up </button>
          <button onClick={() => setYOffset(YOffset + 5)}> Move Down </button>
        </p>
      </div>
      <div style={{ height: 500 }}>
        <pre>Mutation count {mutationCount}</pre>
      </div>
    </>
  );
}

render(<Demo />);
```

### Arguments

| Argument | Type     | Description                                                                                       | Default value                                                           |
| -------- | -------- | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| callback | function | Function which should be invoked on mutation. It is called with the `mutationList` and `observer` | undefined                                                               |
| config   | object   | Mutation Observer configuration                                                                   | {attributes: true,,characterData: true,,subtree: true,,childList: true} |

### Return value

Returns an array with one element

| Argument | Type        | Description                                |
| -------- | ----------- | ------------------------------------------ |
| ref      | CallbackRef | Ref which should be observed for Mutations |

### Basic usage

<iframe src="https://codesandbox.io/embed/usemutationobserverref-2nfih?fontsize=14&hidenavigation=1&theme=dark"
   style={{
    width: "100%",
    height: 500,
    border: 0,
    borderRadius: 4,
    overflow: "hidden"
  }} 
title="useMutationObserver"
allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
/>

## Join Bhargav's discord server

You can click on the floating discord icon at the bottom right of the screen and talk to us in our server.
