# Reproduction of Electron crash when using Yarn PnP

This is a minimum reproduction of an Electron v8 crash when using Yarn PnP.

The crash dump error message is: EXC_BAD_ACCESS / KERN_INVALID_ADDRESS in NodeBindings::CreateEnvironment

To cause the crash, have yarn v2 installed, this package contains it vendored, I have yarn 1.21.1 installed and it automatically uses the v2 vendored copy.

```
yarn install
yarn dev
```

To turn off PnP and use the node_modules linker, go into .yarnrc.yml and uncomment `nodeLinker: node-modules`, it shouldn't crash in this instance.
