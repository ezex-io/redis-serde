# Changes

## 0.13.0

- **Added full serialization support** - This fork extends the original OneSignal/serde-redis crate with complete serialization functionality
- Update to use redis-rs 0.32
- Update to Rust edition 2024
- Full support for serializing Rust types to `redis::Value`
- Support for all common Rust types (primitives, structs, enums, collections, etc.)

## 0.12.0

- Update to use redis-rs 0.21
- Update to use serde_bytes 0.11

## 0.11.0

- Update to use redis-rs 0.20

## 0.10.0

- Update to use redis-rs 0.17

## 0.9.0

- Update to use redis-rs 0.16

## 0.8.0

- Support for borrowing the value passed to deserialization functions

## 0.7.2

- Support for Bytes / ByteBuf deserialization

## 0.7.1

- Support for bool deserialization

## 0.7.0

- Serde 1.0
