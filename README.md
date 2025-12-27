# Negpip - Weighted Prompting for Wan 2.2

Works at CFG=1.0 (Scales V-vectors in cross-attention, no CFG combination).

## Syntax

`(text:weight)` in your positive prompt.

| Weight | Effect |
|--------|--------|
| **< 1.0** | Suppress/reduce |
| **> 1.0** | Boost/amplify |
| **= 1.0** | No effect |

Negative values invert the concept.

## Behavior

- **Suppress** (weight < 1.0): Text removed from prompt, appended separately. Don't put mid-sentence or you'll get gaps like "a woman with walking".
- **Boost** (weight > 1.0): Text stays in prompt for context, plus extra V-scaling

## Examples

Suppress:
```
a woman with black hair. (blonde hair:-1.0)
```

Boost:
```
a cat sitting on a (red couch:1.5)
```

Combined:
```
a man walking through a forest. (rain:-0.5) (fog:1.8)
a man walking through a (foggy:1.8) forest. (rain:-0.5)
```

based on the original from: https://github.com/hako-mikan/sd-webui-negpip



