It is a subset of [[trees]] where it still contains two children, nodes and root node.
- the left value is **less than or equal** to the parent value
- the right value is **greater** than or equal to the parent value

```tikz
\usepackage{tikz}
\usetikzlibrary{backgrounds}

\begin{document}

\begin{tikzpicture}[scale=1.5, level distance=1.5cm,
  level 1/.style={sibling distance=4cm},
  level 2/.style={sibling distance=2cm},
  every node/.style={circle, draw=black, thick, fill=gray!20, text=black, minimum size=10mm},
  show background rectangle,
  background rectangle/.style={fill=white, inner sep=0.3cm}]
  
  \node {8}
    child {node {3}
      child {node {1}}
      child {node {6}
        child {node {4}}
        child {node {7}}
      }
    }
    child {node {10}
      child[missing] {}
      child {node {14}
        child {node {13}}
      }
    };

\end{tikzpicture}

\end{document}

```
<div style="text-align: center">
  Example of a binary search tree
</div>

As there is a structure in terms of value (greater/less) it is extremely useful for sorting purposes and efficient searching properties. 