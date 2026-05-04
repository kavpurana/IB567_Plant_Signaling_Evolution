# Tracing Network Topology and Evolutionary Age of Specialized Metabolic Defense Subnetworks and Core Hormonal Signaling

## Premise
In this study, we aim to compare a core hormonal signaling pathway, jasmonate signaling, with a specialized metabolic defense pathway, glucosinolate biosynthesis, to understand how plant defense systems differ in structure and evolutionary patterns. We focus on *Arabidopsis thaliana* as a model system. Specifically, we will examine whether the jasmonate signaling network is more conserved, while the glucosinolate biosynthesis network shows more variability and recent evolution. By comparing their network structures and enzyme composition, we aim to better understand how plants balance conserved signaling mechanisms with adaptive defense responses.

## Directory Structure

This repository has been organized into specific folders to separate raw data, tabulated data, and network files.

```
.
├── README.md
├── data/
│   ├── csv/
│   │   ├── alpha-linolenic-acid.csv
│   │   └── glucosinolate_biosynthesis.csv
│   └── xml/
│       ├── ath00592.xml
│       └── ath00966.xml
└── networks/
    ├── alpha-linolenic-acid-metabolism.net
    ├── glucosinolate-biosynthesis.net
    ├── glucosinolate_ancestry.vec
    ├── jasmonate_ancestry.vec
    └── plant_signaling_networks.paj
```

### 1. `data/xml/`
This folder contains the raw biological pathway files downloaded from the Kyoto Encyclopedia of Genes and Genomes (KEGG) database in KGML (KEGG XML) format.
*   **`ath00592.xml`**: KEGG pathway for alpha-Linolenic acid metabolism (which leads to jasmonate synthesis) in *Arabidopsis thaliana*.
*   **`ath00966.xml`**: KEGG pathway for Glucosinolate biosynthesis in *Arabidopsis thaliana*.

### 2. `data/csv/`
This folder contains tabular data parsed from the XML files.
*   **`alpha-linolenic-acid.csv`**: Contains enzymes, metabolites, and reaction information extracted from the alpha-linolenic acid metabolism pathway.
*   **`glucosinolate_biosynthesis.csv`**: Contains enzymes, metabolites, and reaction information extracted from the glucosinolate biosynthesis pathway.

### 3. `networks/`
This folder contains the files formatted for network visualization and analysis in Pajek.
*   **`alpha-linolenic-acid-metabolism.net`**: The Pajek network file representing the jasmonate signaling/alpha-linolenic acid metabolism pathway, where nodes are metabolic entities and edges are reactions.
*   **`glucosinolate-biosynthesis.net`**: The Pajek network file representing the glucosinolate biosynthesis pathway.
*   **`jasmonate_ancestry.vec` & `glucosinolate_ancestry.vec`**: Pajek vector files storing node properties. In this case, they represent the evolutionary age or ancestry of the enzymes in the respective networks, allowing nodes to be colored or sized by these attributes in visualizations.
*   **`plant_signaling_networks.paj`**: A comprehensive Pajek project file that bundles both the networks and the ancestry vectors together along with saved layouts and graphical properties.

## How to Run the Pajek Project

To visualize and analyze the networks, you will need to use Pajek, a program designed for large network analysis.

1.  **Install Pajek**: Download and install the latest version of Pajek from its official website (http://mrvar.fdv.uni-lj.si/pajek/). It is available for Windows (or via Wine/virtual machines on macOS/Linux).
2.  **Open Pajek**: Launch the Pajek application.
3.  **Load the Project**:
    *   Navigate to **File > Project > Read** (or use the shortcut `Ctrl+P`).
    *   Browse to the `networks/` directory in this repository.
    *   Select the `plant_signaling_networks.paj` file and click open.
4.  **Visualize the Networks**:
    *   Once loaded, the networks (jasmonate and glucosinolate) will be populated in the **Networks** drop-down menu in the main Pajek window.
    *   To view a network with its evolutionary ancestry, select the network from the **Networks** drop-down list.
    *   Select the corresponding `.vec` file from the **Vectors** drop-down list (e.g., select `glucosinolate_ancestry.vec` when viewing the glucosinolate network).
    *   Go to **Draw > Draw-Partition-Vector** (or press `Ctrl+G` or `Ctrl+V` depending on exactly what you want to draw). This will open the Draw window.
    *   In the Draw window, go to **Options > Colors > Vertices > according to Vector** to color the nodes based on the evolutionary age stored in the vector file. You can also adjust node sizes and layout algorithms (like Kamada-Kawai or Fruchterman-Reingold) within the **Layout** menu to optimize the network visualization.