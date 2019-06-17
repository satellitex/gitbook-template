# Substrate Nodeの起動オプション

FLAGS: 

```text
    --alice Shortcut for --key //Alice --name Alice.
        
    --bob Shortcut for `--key //Bob --name Bob`.

    --charlie
        Shortcut for `--key //Charlie --name Charlie`.

    --dave
        Shortcut for `--key //Dave --name Dave`.

    --dev
        Specify the development chain

    --eve
        Shortcut for `--key //Eve --name Eve`.

    --ferdie
        Shortcut for `--key //Ferdie --name Ferdie`.

    --force-authoring
        Enable authoring even when offline.

-h, --help
        Prints help information

    --light
        Run in light client mode

    --no-grandpa
        Disable GRANDPA when running in validator mode

    --no-mdns
        By default, the network will use mDNS to discover other nodes on the local network. This disables it.
        Automatically implied when using --dev.
    --no-telemetry
        Disable connecting to the Substrate telemetry server (telemetry is on by default on global chains).

    --one
        Shortcut for `--key //One --name One`.

    --rpc-external
        Listen to all RPC interfaces (default is local)

    --two
        Shortcut for `--key //Two --name Two`.

    --validator
        Enable validator mode

-V, --version
        Prints version information

    --ws-external
        Listen to all Websocket interfaces (default is local)
```

OPTIONS: 

```text
    -d, --base-path  Specify custom base path.
    
    --block-construction-execution <STRATEGY>
        The means of execution used when calling into the runtime while constructing blocks. [default: Wasm]
        [possible values: Native, Wasm, Both, NativeElseWasm, NativeWhenPossible]
    --bootnodes <URL>...
        Specify a list of bootnodes

    --chain <CHAIN_SPEC>
        Specify the chain specification (one of dev, local or staging)

    --db-cache <MiB>
        Limit the memory the database cache can use

    --importing-execution <STRATEGY>
        The means of execution used when calling into the runtime while importing blocks. [default: NativeElseWasm]
        [possible values: Native, Wasm, Both, NativeElseWasm, NativeWhenPossible]
        
    --in-peers <IN_PEERS>
        Specify the maximum number of incoming connections we're accepting [default: 25]

    --key <STRING>
        Specify additional key seed

    --keystore-path <PATH>
        Specify custom keystore path

    --listen-addr <LISTEN_ADDR>...
        Listen on this multiaddress

-l, --log <LOG_PATTERN>
        Sets a custom logging filter

    --name <NAME>
        The human-readable name for this node, as reported to the telemetry server, if enabled

    --node-key <KEY>
        The secret key to use for libp2p networking.

        The value is a string that is parsed according to the choice of `--node-key-type` as follows:

        `secp256k1`: The value is parsed as a hex-encoded Secp256k1 32 bytes secret key, i.e. 64 hex characters.

        `ed25519`: The value is parsed as a hex-encoded Ed25519 32 bytes secret key, i.e. 64 hex characters.

        The value of this option takes precedence over `--node-key-file`.

        WARNING: Secrets provided as command-line arguments are easily exposed. Use of this option should be limited
        to development and testing. To use an externally managed secret key, use `--node-key-file` instead.
        
    --node-key-file <FILE>
        The file from which to read the node's secret key to use for libp2p networking.

        The contents of the file are parsed according to the choice of `--node-key-type` as follows:

        `secp256k1`: The file must contain an unencoded 32 bytes Secp256k1 secret key.

        `ed25519`: The file must contain an unencoded 32 bytes Ed25519 secret key.

        If the file does not exist, it is created with a newly generated secret key of the chosen type.
        
    --node-key-type <TYPE>
        The type of secret key to use for libp2p networking.

        The secret key of the node is obtained as follows:

        * If the `--node-key` option is given, the value is parsed as a secret key according to the type. See the
        documentation for `--node-key`.

        * If the `--node-key-file` option is given, the secret key is read from the specified file. See the
        documentation for `--node-key-file`.

        * Otherwise, the secret key is read from a file with a predetermined, type-specific name from the chain-
        specific network config directory inside the base directory specified by `--base-dir`. If this file
        does not exist, it is created with a newly generated secret key of the chosen type.

        The node's secret key determines the corresponding public key and hence the node's peer ID in the context of
        libp2p.

        NOTE: The current default key type is `secp256k1` for a transition period only but will eventually change to
        `ed25519` in a future release. To continue using `secp256k1` keys, use `--node-key-type=secp256k1`.
        [default: Secp256k1]  [possible values: Secp256k1, Ed25519]
        
    --offchain-worker <ENABLED>
        Should execute offchain workers on every block. By default it's only enabled for nodes that are authoring
        new blocks. [default: WhenValidating]  [possible values: Always, Never, WhenValidating]
        
    --offchain-worker-execution <STRATEGY>
        The means of execution used when calling into the runtime while constructing blocks. [default:
        NativeWhenPossible]  [possible values: Native, Wasm, Both, NativeElseWasm, NativeWhenPossible]
        
    --other-execution <STRATEGY>
        The means of execution used when calling into the runtime while not syncing, importing or constructing
        blocks. [default: Wasm]  [possible values: Native, Wasm, Both, NativeElseWasm, NativeWhenPossible]
        
    --out-peers <OUT_PEERS>
        Specify the number of outgoing connections we're trying to maintain [default: 25]

    --pool-kbytes <COUNT>
        Maximum number of kilobytes of all transactions stored in the pool. [default: 10240]

    --pool-limit <COUNT>
        Maximum number of transactions in the transaction pool. [default: 512]

    --port <PORT>
        Specify p2p protocol TCP port. Only used if --listen-addr is not specified.

    --pruning <PRUNING_MODE>
        Specify the pruning mode, a number of blocks to keep or 'archive'. Default is 256.

    --reserved-nodes <URL>...
        Specify a list of reserved node addresses

    --rpc-port <PORT>
        Specify HTTP RPC server TCP port

    --syncing-execution <STRATEGY>
        The means of execution used when calling into the runtime while syncing blocks. [default: NativeElseWasm]
        [possible values: Native, Wasm, Both, NativeElseWasm, NativeWhenPossible]
        
    --telemetry-url <URL VERBOSITY>...
        The URL of the telemetry server to connect to. This flag can be passed multiple times as a mean to specify
        multiple telemetry endpoints. Verbosity levels range from 0-9, with 0 denoting the least verbosity. If no
        verbosity level is specified the default is 0.
        
    --ws-port <PORT>
        Specify WebSockets RPC server TCP port
```

