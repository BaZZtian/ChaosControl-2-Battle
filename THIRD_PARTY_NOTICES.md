# Credits and third-party licenses

ChaosControl 2: Battle is an unofficial PS5 adaptation of the Xbox 360 edition of Sonic Adventure 2. The public repository contains the project page and artwork. The comparison below describes the private PS5 test executable.

## Code used in the PS5 build

The source baseline is [sa2-nx 1.0.4, commit `32a81a8`](https://github.com/ChanseyIsTheBest/sa2-nx/tree/32a81a83aafd83e25d3a3cccae34f567766402c6), by ChanseyIsTheBest and contributors.

| Component | Provenance and PS5 changes |
| --- | --- |
| SA2 application and renderer | The PS5 link includes sa2-nx's application entry and code for game configuration, language, DLC, CPU enhancements, graphics commands, native renderer glue, render targets, texture pools, and shader loading. The compiled copy of `sa2_native_draws.cpp` adds a Prospero guard for GPU heap telemetry. This app code is covered by [GPLv3](licenses/GPL-3.0.txt). Its upstream lineage includes [masseffect-nx](https://github.com/nebadasSwifty/masseffect-nx) by NebadasSwifty and [NFSMW Recompiled](https://github.com/madelrandel-blip/NFSMW-Recompiled) by madelrandel-blip, via [nfsmw-nx](https://github.com/StevensND/nfsmw-nx) by StevensND. |
| Xbox 360 runtime and code generator | sa2-nx's [ReXGlue SDK](https://github.com/rexglue/rexglue-sdk) tree carries work by Tom Clay, the ReXGlue contributors, and Ben Vanik and the [Xenia](https://xenia.jp/) contributors. The PS5 build uses its kernel, filesystem, audio, and graphics code, including modified derivatives such as the Content Manager for empty save directories. The SDK's [BSD 3-Clause notice](licenses/ReXGlue-BSD-3-Clause.txt) applies to that code. |
| Audio decoding | The private PS5 link includes FFmpeg 4.4 libavcodec and libavutil, built with the XMA2 and adapted XMAFrames decoders. The selected configuration disables GPL, version-3 and nonfree components. FFmpeg and its contributors retain their notices; the selected libraries are covered by [LGPL 2.1](licenses/FFmpeg-LGPL-2.1.txt). The corresponding modified source and build configuration must accompany distribution under the applicable terms. |
| Generated game code | The build recompiles the Xbox 360 title and its data module. PS5 changes include the offline menu's draw and navigation behavior. The original game logic and assets remain the work of SEGA and the respective rightsholders. |
| PS5 integration | ChaosControl contributors added the Prospero entry and lifecycle integration, controller and presentation adapters, module admission, title-specific file and save handling, and the PS5 UI and artwork changes. Those changes include newly authored adapters and edits to inherited or generated code. |

Against the pinned baseline, 23 direct link inputs matched their primary sa2-nx application source and 90 matched their primary SDK source after line-ending normalization. These are source-file matches from the checked-out inputs and compilation recipes. They do not measure the percentage of the binary or whether included headers and compiler settings match. Other inputs include adapted copies, integration code, libraries, and generated archives.

See the [upstream third-party notices at the pinned commit](https://github.com/ChanseyIsTheBest/sa2-nx/blob/32a81a83aafd83e25d3a3cccae34f567766402c6/THIRD_PARTY_NOTICES.md) for the original dependency and license breakdown. The Switch renderer and platform dependencies listed there should not be read as a bill of materials for the PS5 executable.

## Distribution

The repository's [MIT notice](LICENSE) does not license the private PS5 executable, upstream code, or original game content. A public package containing the GPL-covered application code must satisfy the GPL's distribution terms, including access to the corresponding source for the distributed build. The package also needs the applicable notices and license material for its selected libraries. The current repository does not provide that package or its corresponding source.
