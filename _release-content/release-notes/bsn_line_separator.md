---
title: BSN Line Separator Syntax
authors: ["@cart"]
pull_requests: [25626]
---

BSN syntax historically could result in some over-indentation (and line noise) if you want visible clarity between entities in a list:

```rust
bsn! {
    Node 
    Children [
        (
            #OkButton
            @button("Ok")
        ),
        (
            #CancelButton
            @button("Cancel")
        ),
    ]
}
```

It technically supports omitting the `()`, but this degrades clarity:

```rust
bsn! {
    Node 
    Children [
        #OkButton
        @button("Ok"),
        #CancelButton
        @button("Cancel"),
    ]
}
```

**Bevy 0.20** introduces a new (optional) `---` separator to achieve both terseness and clarity!

```rust
bsn! {
    Node 
    Children [
        #OkButton
        @button("Ok")
        ---
        #CancelButton
        @button("Cancel")
    ]
}
```
