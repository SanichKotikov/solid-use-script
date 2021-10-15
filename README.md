# solid-use-script

Solid hook to dynamically load an external script.

```bash
npm i -S solid-use-script
```

## Usage

```typescript jsx
import { Switch, Match } from 'solid-js';
import { useScript } from 'solid-use-script';

function App() {
  const [loading, error] = useScript('https://some.api');

  return (
    <Switch fallback={<ApiProvider>...</ApiProvider>}>
      <Match when={loading()}>Loading API...</Match>
      <Match when={error()}>Failed to load API: {error().message}</Match>
    </Switch>
  );
}
```

### Attributes

```typescript
useScript('https://some.api', { crossorigin: 'anonymous' });
```
