# Negpip - Experimental Weighted Prompting for Wan 2.2

Experimental fork. Scales K and V vectors in cross-attention. Works at CFG=1.0.

Based on: https://github.com/hako-mikan/sd-webui-negpip

## Syntax

`(text:weight)` - values below 1.0 suppress, above 1.0 boost.

Effective range roughly **-1.5 to 1.5**. Higher values can cause artifacts depending on the model. Results vary depending on phrasing.
In general the negative weighting seems to be a bit more effective. Can get some nice results sometimes but I'll probably not keep this updated.

V-only version available at commit [115809c](https://github.com/amatiramisu/ComfyUI-WanVideoWrapper-negpip/commit/115809c)

## Examples

- a woman with black hair. (blonde hair:-1.0)
- a cat sitting on a (red couch:1.3)

Suppress phrases should be separate, not mid-sentence.
