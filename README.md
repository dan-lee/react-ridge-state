# react-ridge-state :weight_lifting_woman: ⚡️ :weight_lifting_man:

**Simple** :muscle: **fast** ⚡️ and **small** :balloon: (0.8kb) global state management for React which does not get in your way.

```
yarn add react-ridge-state
```

or

```
npm install react-ridge-state --save
```

## Why another state library :thinking:

We were frustrated that the current solutions could often only be used from React or have too complicated APIs. We wanted a lightweight solution with a smart API that can also be used outside React components.

## Features :woman_juggling:

- React / React Native
- Simple
- Fast
- Very tiny
- 100% Typesafe
- Hooks
- Use outside React components

## Roadmap :running_woman: :running_man:

- Persistent (probably another libary)

## Getting started :clap: :ok_hand:

### Create a new state

```typescript
import { newRidgeState } from "react-ridge-state";
interface CartProduct {
  id: number;
  name: string;
}
const defaultState: CartProduct[] = [{ id: 1, name: "Product" }];
export const cartProductsState = newRidgeState<CartProduct[]>({
  key: "CartState", // needs to be unique across other global state
  defaultState,
});
```

### Use state inside components

```typescript
import { useRidgeState } from "react-ridge-state";

const [cartProducts, setCartProducts] = useRidgeState(cartProductsState);
```

### Use state outside of React

```typescript
import { getRidgeState } from "react-ridge-state";
getRidgeState(cartProductsState);
```

### Set state outside of React

```typescript
import { setRidgeState } from "react-ridge-state";
setRidgeState(cartProductsState, [{ id: 1, name: "NiceProduct" }]);
```
