## What is Recoil ?
>> Recoil is a state management library for React applications.

# Atom :
>> Atoms are units of state in Recoil. They represents individual pieces of application state. You can create atoms using the atom() function provided by Recoil. Atom can hold single value which can be either primitive, object or array.
```js
        import { atom } from 'recoil';

        export const countAtom = atom({
            key:'countAtom',
            default: 0,
        });
```

# useRecoilState :
>> This hook returns a tuple containing the current value of the Recoil state and a function to set its new value.
```js
        const [count, setCount] = useRecoilState(countAtom);
```

# useRecoilValue :
>> This hook retrieves and subscribes to the current value of a Recoil state.
```js
        const count = useRecoilValue(countAtom);
```

# useSetRecoilState :
>> This hook returns a function that allows you to set the value of a Recoil state without subscribing to updates.
```js
        const setCount = useSetRecoilState(countAtom);
```

# RecoilRoot :
>> The RecoilRoot is a component provided by Recoil that serves as the root of the Recoil state tree. It must be placed at the top level of your React component tree to enable the use of Recoil atoms and selectors throughout your application.
```js
        import { RecoilRoot } from 'recoil';
        import App from './App';

        export default function() {
            return (
                <RecoilRoot>
                <App />
                </RecoilRoot>
            );
        };
```

# Selector :
>> Selectors are derived state in Recoil. They compute values based on atoms and other selectors. 
```js
        import { atom, selector } from 'recoil';

        // Atoms
        export const quantityAtom = atom({
        key: 'quantityAtom',
        default: 1,
        });

        export const priceAtom = atom({
        key: 'priceAtom',
        default: 10,
        });

        // Selector
        export const totalCostSelector = selector({
        key: 'totalCostSelector',
        get: ({ get }) => {
            const quantity = get(quantityAtom);
            const price = get(priceAtom);
            return quantity * price;
        },
        });
```