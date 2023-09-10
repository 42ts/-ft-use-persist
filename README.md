# use-persist - react `usePersist` hook

have something like member variable of class component, in function component.

## Usage

```jsx
import { usePersist } from '@-ft/use-persist';

function AppContextProvider({ children }) {
  const persist = usePersist(null);
  useEffect(() => {
    persist.current = initializeSomething();
    return () => {
      persist.current.dispose();
      persist.current = null;
    };
  }, []);
  return (
    <AppContext.Provider value={persist.current}>
      {children}
    </AppContext.Provider>
  );
}
```
