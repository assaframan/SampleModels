# SampleModels — text-to-3D meshes for animeshy demos

Twenty textured `.glb` source meshes used as the corpus for the **[animeshy](https://github.com/assaframan/animeshy)** rigging + LLM-keyframing pipeline (Liveupmesh paper).

Each mesh was generated with **Meshy** text-to-3D under the *rigging-pose discipline* described in the paper (limbs spread, no contact with the body) so a downstream auto-rigger (RigAnything, Gemini-designed Blender pipeline) can find every appendage. None of these have skeletons or skin weights — they are the *input* to the rigging stage.

## Models

| ID | Topology |
|---|---|
| `humanoid-f`, `humanoid-m`, `robot`, `chubby-cat`, `chubby-teddy` | biped, 2 arms |
| `chubby-snowman` | armed-but-legless |
| `chubby-penguin` | flipper-armed biped |
| `chubby-octopus` | radial, 8 tentacles |
| `mermaid` | arms + tail (no legs) |
| `durga` | biped + 6 arms |
| `alien-3a4l` | 3 arms + 4 legs |
| `centaur` | 2 arms + 4 legs |
| `wolf`, `horse` | quadruped |
| `dragon-quad`, `cerberus` | quadruped (winged / 3-headed) |
| `eagle` | bird (2 wings + 2 legs) |
| `mantis` | hexapod (6 legs + 2 raptorial arms) |
| `spider` | octopod (8 legs) |
| `serpent` | limbless |

## Use in a Colab

```python
import os, subprocess
os.makedirs('/content/models', exist_ok=True)
subprocess.run(['git', 'clone', '--depth=1', 'https://github.com/assaframan/SampleModels.git', '/content/models'], check=True)
# Now /content/models/dragon-quad.glb, /content/models/spider.glb, etc.
```

## License

Each `.glb` is generated content from Meshy's text-to-3D service; check Meshy's terms for redistribution. The README + repo structure are MIT (see LICENSE).
