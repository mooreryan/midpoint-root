# Midpoint Rooting Trees

## Installing ETE

If you don't have anaconda/miniconda installed, first install that.

Create a conda environment for ete.

```
conda create --name ete
```

Install software.

```
conda install -c etetoolkit ete3 ete_toolchain
```

Get some coffee, it takes a few minutes.

Activate the conda environment whenever you want to use `ete3`.

```
conda activate ete
```

Check it if you want.

```
ete3 build check
```

When you're done with `ete3`, deactivate the conda environment.

```
conda deactivate
```

## Run the little script

Here is a script for midpointing rooting a tree.

```python
import sys

from ete3 import Tree

intre = sys.argv[1]

tre = Tree(intre, quoted_node_names=True)

# Calculate the midpoint node
midpoint = tre.get_midpoint_outgroup()

# Set midpoint as outgroup.
tre.set_outgroup(midpoint)

print(tre.write())
```

Save that as `midpoint-root.py` or whatever you like.

### Run it

```
python midpoint-root.py my-tree.tre > my-tre.rooted.py
```

If python 3 isn't your default, you may need to type `python3` instead.