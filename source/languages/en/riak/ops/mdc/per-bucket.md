---
title: "Multi Data Center Replication: Per Bucket"
project: riak
header: riakee
version: 1.1.0+
document: cookbook
toc: true
audience: intermediate
keywords: [mdc, repl, bucket]
moved: {
    '2.0.0-': 'riakee:/cookbooks/Multi-Data-Center-Replication-Pre-Bucket'
}
---

To enable or disable replication per bucket, you can use the `repl`
bucket property.

Some changes have occurred between 1.1 and 1.2.

These `repl` values are available in Riak Enterprise version 1.1 and
above:

  * `true` --- Enable replication (realtime + fullsync)
  * `false` --- Disable replication (realtime + fullsync)

These option values are only available in Riak Enterprise version 1.2
and above:

  * `realtime` --- Replication only occurs in realtime for this bucket
  * `fullsync` --- Replication only occurs during a fullsync operation
  * `both` --- Replication occurs in realtime and during fullsync

### Example of Disabling

```curl
curl -v -XPUT http://127.0.0.1:8091/riak/my_bucket \
  -H "Content-Type: application/json" \
  -d '{"props":{"repl":false}}'
```

### Example of Enabling

```curl
curl -v -XPUT http://127.0.0.1:8091/riak/my_bucket \
  -H "Content-Type: application/json" \
  -d '{"props":{"repl":true}}'
```
