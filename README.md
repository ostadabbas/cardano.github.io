# Cardano — project page

Source for the Cardano project page.

**Live site:** https://ostadabbas.github.io/cardano.github.io/

## Project links

| | |
|---|---|
| **Project page** | https://ostadabbas.github.io/cardano.github.io/ |
| **Code** | https://github.com/ostadabbas/Cardano |
| **Weights, heads and results** | https://huggingface.co/bishoygaloaa/cardano |
| **Working repository** (lab, private) | https://bitbucket.org/aclabneu/cardano |

## Authors

- **Bishoy Galoaa**<sup>1</sup>
- **Sadid A. Hasan**<sup>2</sup>
- **Sarah Ostadabbas**<sup>1</sup>

<sup>1</sup> Northeastern University — [neu.edu](https://www.neu.edu)
<sup>2</sup> Microsoft — [microsoft.com](https://www.microsoft.com)

Augmented Cognition Lab, Northeastern University.

## What Cardano is

A streaming video-language model that decides, while the video is still playing, that watching
more of it would not change its answer — and stops there. The decision is a 40-parameter linear
head on nine features of the model's own answer distribution: no hidden state, one global
operating point, no per-dataset tuning.

## Repository layout

```
index.html            the page (single file, no build step)
static/
  pipeline.png        method figure
  pareto.png          accuracy vs. fraction watched
  vru.png             the safety-critical qualitative episode
  teaser.jpg          social preview image
  episodes.json       per-window data for the supplementary episodes
media/                128 window frames, 8 episodes x 16 windows
```

## Supplementary episodes

Eight episodes are shown on the page, each as all sixteen windows with the commit window boxed
and every later window faded because the model never encoded it. `static/episodes.json` carries
the underlying data per episode: question, options, gold answer, the per-window answer and top
probability, the commit window, and the whole-clip answer.

Two of the eight are **failure cases**, included deliberately rather than filtered out.

## Serving locally

No build step — it is one HTML file plus assets. Any static server works:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Publishing

GitHub Pages, served from `main` at the repository root. In **Settings → Pages**, set
*Source* to "Deploy from a branch", *Branch* to `main`, and the folder to `/ (root)`.

## Notes

- Video corpora are not redistributed. The frames on the page are short excerpts shown for
  illustration; the underlying clips come from their original benchmarks under their own
  licences.
- Images carry no EXIF or location metadata.
