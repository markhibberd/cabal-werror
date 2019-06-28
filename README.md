# cabal new-build Werror on dependencies


```
git clone https:://github.com/markhibberd/cabal-werror
cabal new-build --ghc-options="-Wall -Werror"
```


Results in:
```
[  1 of 112] Compiling Control.Concurrent.Compat ( src/Control/Concurrent/Compat.hs, dist/build/Control/Concurrent/Compat.o )

src/Control/Concurrent/Compat.hs:4:14: error: [-Wtrustworthy-safe, -Werror=trustworthy-safe]
    ‘Control.Concurrent.Compat’ is marked as Trustworthy but has been inferred as safe!
  |
4 | {-# LANGUAGE Trustworthy #-}
  |              ^^^^^^^^^^^

src/Control/Concurrent/Compat.hs:8:3: error: [-Wduplicate-exports, -Werror=duplicate-exports]
    ‘forkFinally’ is exported by ‘forkFinally’ and ‘module Base’
  |
8 | , forkFinally
  |   ^^^^^^^^^^^

src/Control/Concurrent/Compat.hs:9:3: error: [-Wduplicate-exports, -Werror=duplicate-exports]
    ‘forkOSWithUnmask’ is exported by ‘forkOSWithUnmask’ and ‘module Base’
  |
9 | , forkOSWithUnmask
  |   ^^^^^^^^^^^^^^^^
cabal: Failed to build base-compat-0.10.5 (which is required by exe:example
from example-0.1.0.0). See the build log above for details.
```
