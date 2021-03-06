# rnnoise-nodejs

[![Build Status](https://travis-ci.com/cedrickchee/rnnoise-nodejs.svg?branch=master)](https://travis-ci.com/cedrickchee/rnnoise-nodejs)

Node.js bindings to Xiph's [RNNoise denoising C library](https://github.com/xiph/rnnoise/).

[RNNoise](https://people.xiph.org/~jm/demo/rnnoise/) is a project showing how deep learning (Recurrent Neural Networks/RNNs) can be applied to noise suppression.

## Install

[![NPM](https://nodei.co/npm/rnnoise.png?compact=true)](https://nodei.co/npm/rnnoise/)

## Use

```javascript
const rnnoise = require("rnnoise");

const denoisedBufLength = rnnoise.suppress(
  "babble_15dB.wav",
  "babble_15dB_dn.wav"
);

console.log(`Denoised buffer length: ${denoisedBufLength} bytes`);
```

---

## API

### Noise Suppression Functions

**rnnoise.suppress(input: string, output: string)**

**suppress** operates on 16-bit RAW audio format (machine endian) mono PCM files sampled at 48 kHz. The output is also a 16-bit RAW PCM file.

- `input` is a required string of the path to RAW PCM file input.
- `output` is a required string of the path to output RAW PCM file.

## Developer

**Working on project with [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)**

We keep a [rnnoise Git repo](https://github.com/xiph/rnnoise/) as a subdirectory in this Git repo. So, please clone this repo by using Git submodule:

```
git clone --recursive https://github.com/cedrickchee/rnnoise-nodejs.git
```

---

<details>

<summary><b>Expand License</b></summary>

The code in this repository, including all code samples, is released under the [MIT license](LICENSE).

Copyright (c) 2020 Cedric Chee
</details>
