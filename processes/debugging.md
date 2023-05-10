# Debugging RPCh

This guide aims to help you create [bug reports](https://github.com/Rpc-h/RPCh/issues/new?assignees=&labels=bug&projects=&template=bug.md&title=)
when you run into issues with RPCh.

Please follow on of the following scenarios:

- (1) using an extension which integrates the [RPCh SDK](https://github.com/Rpc-h/RPCh/tree/main/packages/sdk#rpch-sdk)
- (2) using an extension via custom network and [rpc-server](https://github.com/Rpc-h/RPCh/tree/main/apps/rpc-server#rpch-rpc-server)
- (3) using the SDK in your application

## Scenarios

### Using an extension which integrates the RPCh SDK

1. Go to [access.rpch.net](https://access.rpch.net/) and click `Try out with docker`.
2. Ensure that `rpc-server` has been started with the `DEBUG="rpch*"` flag.
3. Go to your wallet, and add the custom network URL given to you by [access.rpch.net](https://access.rpch.net/).
4. Once you attach the network URL to your wallet, you should be able to see activity in the logging of your `rpc-server`.
   1. If you see activity, but wallet is not usable, go to step (5).
   2. If you don't see activity, this means the wallet is not sending traffic to `rpc-server`.
      1. Ensure that `rpc-server` is accessible to the correct PORT and no other process is using it.
      2. Go to step (5)
5. Open a bug report while following the bug report's template instructions.

### Using an extension via custom network and rpc-server

1. Ensure that `rpc-server` has been started with the `DEBUG="rpch*"` flag.
2. Once you attach the network URL to your wallet, you should be able to see activity in the logging of your `rpc-server`.
   1. If you see activity, but wallet is not usable, go to step (3).
   2. If you don't see activity, this means the wallet is not sending traffic to `rpc-server`.
      1. Ensure that `rpc-server` is accessible to the correct PORT and no other process is using it.
      2. Go to step (3)
3. Open a bug report while following the bug report's template instructions.

### Using the SDK in your application

1. Enable `debugging` with the following `sdk.debug.enable("rpch*")`. Most of the times, this is sufficient you know where the blocker is.
2. Ensure that the SDK has been started `sdk.isReady`. If this is `true` it means the SDK has been correctly initialized and ready to send traffic.
3. Send a Request using `sdk.sendRequest`. You should see sending logs in your terminal which look somewhat like `sending message to HOPRd node 4|514266|1|2`.
4. Once the request has been resolved, you should be able to see a response with the same ID, in our example, that is `514266`.

If logging is not sufficient to help you understand where the problem is, reach out to our [discord](https://discord.com/invite/VRyTQTNBTy) for help.
