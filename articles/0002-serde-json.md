jsonのparseとbuild
```rust
use serde_json::json;
use serde_json::Value;
fn main() -> Result<(), serde_json::Error> {
    let json_str = r#"{"name": "John Doe", "age": 30, "is_student": false}"#;
    let parsed:Value = serde_json::from_str(json_str)?;
    println!("{}", parsed["name"].to_string());
    let j = json!(
        {
            "name": "John Doe",
            "age": 30,
            "is_student": false,
            "courses": ["Math", "Science"]
        }
    );

    println!("{}", j["name"]);
    Ok(())
}
```

```toml
[package]
name = "serde_json-sample"
version = "0.1.0"
edition = "2024"

[dependencies]
serde_json = "1.0"
anyhow = "1.0"
```