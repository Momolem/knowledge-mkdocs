---
share: true
---
>[!info] Source
>https://protobuf.dev/overview/

It’s like JSON, except it’s smaller and faster, and it generates native language bindings. You define how you want your data to be structured once, then you can use special generated source code to easily write and read your structured data to and from a variety of data streams and using a variety of languages.

Protocol buffers are a combination of the definition language (created in `.proto` files), the code that the proto compiler generates to interface with data, language-specific runtime libraries, and the serialization format for data that is written to a file (or sent across a network connection).

## What Problems do Protocol Buffers Solve?

Protocol buffers provide a serialization format for packets of typed, structured data that are up to a few megabytes in size. The format is suitable for both ephemeral network traffic and long-term data storage. Protocol buffers can be extended with new information without invalidating existing data or requiring code to be updated.

Protocol buffers are the most commonly-used data format at Google. They are used extensively in inter-server communications as well as for archival storage of data on disk. Protocol buffer _messages_ and _services_ are described by engineer-authored `.proto` files. The following shows an example `message`:

```protobuf
message Person {
  optional string name = 1;
  optional int32 id = 2;
  optional string email = 3;
}
```