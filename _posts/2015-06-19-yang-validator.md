---
layout: post
title: For your YANG validation needs
---

With the barrage of new YANG models being proposed in the IETF, we have been struggling to keep up with making sure that that the quality of the modules themselves are ok. We needed a web UI and REST interface to allow people to validate uploaded or hosted YANG modules in IETF draft and RFC formats. So we built one based on some previous open source work in the YANG community (e.g. [pyang](https://github.com/mbj4668/pyang) and [xym](https://github.com/YangModels/yang/tree/master/tools/xym))

There's a hosted instance runnig on [yangvalidator.org](yangvalidator.org) and the code is in [github](https://github.com/cmoberg/bottle-yang-extractor-validator).