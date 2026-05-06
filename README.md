# Rbx-Dom
Rust shared library for parsing **.rbxl** files

# API
```rust
// Part data structure
struct RbxlPartData {
    name: *const c_char,
    position: [f32; 3],
    size: [f32; 3],
    orientation: [f32; 3],
    color: [u8; 3],
    transparency: f32,
    anchored: bool
}

// Load the rbxl file and get parts array as raw pointer
fn rbxlLoad(path: *const c_char, out_count: *mut usize) -> *mut RbxlPartData

// Free parts array
fn rbxlFree(ptr: *mut RbxlPartData, count: usize)
```