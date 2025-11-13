# redis-serde

[serde][] serialization and deserialization of [redis-rs][] values

[serde]: https://github.com/serde-rs/serde
[redis-rs]: https://github.com/mitsuhiko/redis-rs

## About

This crate is a fork of [OneSignal/serde-redis](https://github.com/OneSignal/serde-redis) with **full serialization support** added.

## Status

- ✅ Deserialization: Fully implemented and working
- ✅ Serialization: Fully implemented and working

## Summary

This crate provides automatic serialization and deserialization of values for use with redis-rs.

### Deserialization

```rust
use redis-serde::RedisDeserialize;

#[derive(Debug, Deserialize, PartialEq)]
struct Simple {
    a: String,
    b: String,
}

let s: Simple = redis.hgetall("simple_hash")?
                     .deserialize()?;
```

### Serialization

```rust
use redis-serde::Serializer;
use serde::Serialize;

#[derive(Debug, Serialize, PartialEq)]
struct Simple {
    a: String,
    b: String,
}

let data = Simple {
    a: "value1".to_string(),
    b: "value2".to_string(),
};

let redis_value = data.serialize(Serializer)?;
// Use redis_value with redis-rs commands
```

## Features

- **Deserialization**: Convert `redis::Value` types into Rust types using serde
- **Serialization**: Convert Rust types into `redis::Value` types using serde
- Support for all common Rust types (primitives, structs, enums, collections, etc.)
- Compatible with redis-rs 0.32+

## License

Licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.

