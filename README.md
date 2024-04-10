# tauri-plugin-nosleep-fork

Tauri plugin to block the power save functionality in the OS

```rust
fn main() {
  tauri::Builder::default()
    .plugin(tauri_plugin_nosleep::init())
    .run(tauri::generate_context!())
    .expect("failed to run app");
}
```


Add the NPM package.

```console
npm install tauri-plugin-nosleep-api-fork
# or
yarn add tauri-plugin-nosleep-api-fork
```


Then add these permissions to your App capabilities.

```json
{"permissions": [
    "nosleep:allow-unblock",
    "nosleep:allow-block",
  ]
}
```


Use this within TS/JS.

```js
import { block, NoSleepType, unblock } from 'tauri-plugin-nosleep-api-fork'
block(NoSleepType.PreventUserIdleDisplaySleep);
// To unblock whenever you are done
unblock();
```