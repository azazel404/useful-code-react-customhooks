# Useful Code Custom React Hooks

A simple package useful-custom-react-hooks

## Installation

You can install the package using npm:

```
npm i useful-code-react-customhooks
```

## Usage

Use Toggle

```
import { useToggle } from 'useful-code-react-customhooks';

export default function ToggleComponent() {
  const [value, toggleValue] = useToggle(false)

  return (
    <div>
      <div>{value.toString()}</div>
      <button onClick={toggleValue}>Toggle</button>
      <button onClick={() => toggleValue(true)}>Make True</button>
      <button onClick={() => toggleValue(false)}>Make False</button>
    </div>
  )
}

```

Use Array

```
import { useArray } from 'useful-code-react-customhooks';

 export default function ArrayComponent() {
  const { array, set, push, remove, filter, update, clear } = useArray([
    1, 2, 3, 4, 5, 6,
  ])

  return (
    <div>
      <div>{array.join(", ")}</div>
      <button onClick={() => push(7)}>Add 7</button>
      <button onClick={() => update(1, 9)}>Change Second Element To 9</button>
      <button onClick={() => remove(1)}>Remove Second Element</button>
      <button onClick={() => filter(n => n < 3)}>
        Keep Numbers Less Than 4
      </button>
      <button onClick={() => set([1, 2])}>Set To 1, 2</button>
      <button onClick={clear}>Clear</button>
    </div>
  )
}
```

Use useTimeout

```
import { useState } from "react"
import { useTimeout } from 'useful-code-react-customhooks';

export default function TimeoutComponent() {
  const [count, setCount] = useState(10)
  const { clear, reset } = useTimeout(() => setCount(0), 1000)

  return (
    <div>
      <div>{count}</div>
      <button onClick={() => setCount(c => c + 1)}>Increment</button>
      <button onClick={clear}>Clear Timeout</button>
      <button onClick={reset}>Reset Timeout</button>
    </div>
  )
}
```
