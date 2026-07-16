# Luau Binary Serializer

Luau Binary Serializer compresses your Roblox data tables into compact, lightweight binary streams. Built entirely on Roblox's native `buffer` API, this module provides a fast, bandwidth-friendly alternative to standard JSON formatting. 

You can use this tool to optimize network payloads sent over `RemoteEvents` or to reduce character usage when saving data to `DataStores`.

## Features

* **Native Buffer Implementation:** Bypasses table-generation overhead by reading and writing bytes directly.
* **Smart Numeric Packing:** Automatically selects the smallest numeric representation (u8, i16, i32, or f64) based on the value to minimize file size.
* **Varint Support:** Uses Variable-length Quantity encoding to represent string lengths and table indices using the fewest bytes possible.
* **Roblox Type Support:** Serializes `nil`, `boolean`, `number`, `string`, `table`, `Vector3`, and `CFrame` values natively.
* **Integrated Base64 Utilities:** Encodes binary buffers to safe ASCII strings for direct compatibility with Roblox DataStores.

## Installation

### Manual Installation
1. Copy the source code from `src/BinarySerializer.luau`.
2. Create a `ModuleScript` inside `ReplicatedStorage` and name it `BinarySerializer`.
3. Paste the code directly into that script.

### Rojo Setup
Place the `src` folder inside your project directory and map it in your `default.project.json` file:

```json
"ReplicatedStorage": {
  "BinarySerializer": {
    "$path": "src/BinarySerializer.luau"
  }
}
