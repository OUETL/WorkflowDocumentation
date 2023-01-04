# ChimeraX Condensed Guide

## General Program Information
ChimeraX is an application for molecular visualization and analysis, with an emphasis on molecular assemblies. It can be downloaded free of charge for academic, government, nonprofit, and personal use. Visit the UCSF ChimeraX page at https://www.cgl.ucsf.edu/chimerax/index.html for more information. 

## Navigating the Program
### Interface
- The **Working Pane** is the area where the model is loaded and viewed.
- The **Tab Groups**, Home, Molecule Display, Nucleotides, Graphics, Map, Medical Image, Markers, and Right Mouse, are displayed at the top of the program underneath the menu.
- The **Log Pane** to the right displays model information and logs changes made to the model.
- The **Models Pane** under the Log Pane details the model parts and colors.
- The **Command Line** spans across the bottom of the program and is used to input commands.
![Screenshot of the ChimeraX user interface. See information above.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/chimerax-default-interface.png)

### Loading Proteins
Proteins can be downloaded from the internet and loaded into the program’s workspace. They can also be directly loaded into the program’s workspace using the command line. 
- Navigate to RCSB at https://www.rcsb.org/ to download proteins. 
  1. Search for the desired protein in the search bar in the top right.
  2. Click on the protein, click on the **Download Files** button in the top right, then download the **PDB Format** file without the (gz) tag.
  3. In ChimeraX, click **Open** from the **Home** tab and select the protein.
- If there is an internet connection, proteins can instead be directly called using the command `open` and the name of the file in the command line. For example: `open 1stp`

### Basic controls
- Click and hold on the model to move it about the vertical and horizontal axis.
- Click and hold on the black space to rotate the model.
- Right click and hold to move the center of the model about the screen.
- Use the scroll wheel to zoom in and out on the model.

## Model Preparation
### Selecting parts
![Screenshot of a highlighted ligand.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/selected-highlight.PNG)
To select residues, hold **Ctrl** and click on the desired part. Selections will be highlighted with a thin green outline. Expand or lessen the selection by pressing up or down on the arrow keys from the keyboard.
  - To select residues using the command line, use the `sel` command and the molecule code or atom code to be selected. For example: `sel :108` or `sel :ALA`
- To deselect residues, hold **Ctrl** and click on a blank space in the workspace.
  - To deselect residues using the command line, use the command `sel clear`

### Showing and hiding parts
![The Show Atoms, Hide Atoms, Show Cartoons, and Hide Cartoons buttons are located in the middle of the Home tab group.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/show-hide-atoms-cartoons.png)
- To hide all atoms, click the **Hide Atoms** button under the **Home** tab.
  - To hide all atoms using the command line, use the command `hide`
- To hide only specific atoms, first select them, then click the **Hide Atoms** button under the Home tab.
  - To hide only specific atoms using the command line, first select the atoms, then use the command `hide sel`
  - It is also possible to hide specific atoms by using the command `hide`, a colon (:), and a molecule code or atom code. For example: `hide :88` or `hide :TRP`
- To hide all ribbons, click the **Hide Cartoons** button under the **Home** tab.
  - To hide all ribbons using the command line, use the command `hide ribbons`
- To hide only specific ribbons, first select them, then click the **Hide Cartoons** button under the Home tab.
  - To hide only specific ribbons using the command line, first select the ribbons, then use the command `hide sel ribbons`
- To show all atoms and ribbons, click the **Show Atoms** and **Show Cartoons** buttons under the **Home** tab.
  - To show all atoms and ribbons using the command line, use the commands `show` and `show ribbons` respectively.
- To reset the look of the model, go to the program’s menu, click on **Presets**, then **Original Look**.

### Coloring parts
![ALT TEXT HERE COME BACK LATER](![image](https://user-images.githubusercontent.com/70342309/210636599-1ec8f35b-ad94-4b1d-b139-4baf1c4aa630.png)
- To change the color of the entire protein, click on the colored box in the bottom right panel labeled **Models**. Choose a new color either by clicking on a default basic color, entering a hex code in the HTML input box, or selecting a custom color from the large color gradient.
  - To change the color of the entire protein using the command line, use the `color` command and the name or hex code of the new color. For example: `color green` or `color #40526B`
- To change the color of a specific part of the protein, first select the parts of the protein that needs to be changed, then use the command `color sel` and the name or hex code of the new color. For example: `color sel green` or `color sel #FFC0CB`

![The Heteroatom button is located in the middle of the Molecule Display tab group.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/heteroatom.png)

- To color the protein in standard heteroatom colors, click the **Heteroatom** button underneath the **Molecule Display** tab.
  - To color the protein in the standard heteroatom colors in the command line, use the command `color byhet`

### Showing and hiding labels
- To show all labels on residues, use the command `label @@display`
  - To show only specific labels on residues, use the command `label @@display`, a colon (:), and the molecule code or atom code. For example: `label :ALA @@display` or `label :300 @@display`
- To delete all labels, use the command `label delete`
  - To delete only specific labels, use the command `label delete`, a colon (:), and the molecule code or atom code. For example: `label delete :ALA` or `label delete :300`
  - To delete ligand labels, use the command `label delete ligand`
- To change the color of all labels, use the command `label color` and the name or hex code of the new color. For example: `label color green` or `label color #FFC0CB`
  - To change the color of only specific labels, use the command `label color`, a colon (:), the molecule code or atom code, and the name or hex code of the new color. For example: `label :ALA color green` or `label :300 color #FFC0CB`
- To change the size of all labels, use the command `label height` and the new numerical size. For example: `label height 2`
  - To change the size of only specific labels, use the command `label height`, a colon (:), the molecule code or atom code, and the new numerical size. For example: `label :ALA height 4` or `label :300 height 3`

### Finding H-Bond contacts
![The H-bonds and Hide H-bonds buttons are located on the right of the Molecule Display tab group.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/hbond.png)
- To find all estimated H-Bonds, click on the **H-Bonds** button under the **Molecule Display** tab.
  - To find all estimated H-Bonds using the command line, use the command `hbonds`
- To find only specific H-Bonds, select part of the structure and click on the **H-Bonds** button under the **Molecule Display** tab.
  - To find only specific H-Bonds using the command line, use the command `hbonds` followed by a colon (:) and the molecule code or atom code. For example: `hbonds :BTN` or `hbonds :23`
  - To find contacts between ligands and nearby residues, use the command `hbonds ligand`
- To hide all H-Bonds, click on the **Hide H-Bonds** button under the **Molecule Display** tab.
  - To hide all H-Bonds using the command line, use the command `hide hbonds`
- To change the color of H-Bonds, use the command `color hbonds` and the name or hex code of the new color. For example: `color hbonds magenta`  or `color hbonds #FFAE42`
- To mark the distance of all H-Bonds in Angstroms, use the command `hbonds showdist true`
  - To mark the distance of only specific H-Bonds, use the command `hbonds showdist true`, a colon (:) and a molecule code or atom code. For example: `hbonds :BTN showdist true` or `hbonds :300 showdist true`

### Using the Sequence Pane
![The Sequence button is located on the right of the Molecule Display tab.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/sequence-pane.png)
- Open the Sequence Pane by clicking the **Sequence** button under the **Molecule Display** tab. The Sequence Pane will display in the bottom right of the program.
- Select regions by clicking on highlighted colors in the Sequence Pane.
  - Select other specific regions by clicking and dragging on sections of a chain in the Sequence Pane.
- Color regions by first selecting them, then using the `color sel` command and the name or hex code of the new color. For example: `color sel yellow` or `color sel #40526B`
- Important things to note about the sequence pane:
  - Yellow regions are α-helixes.
  - Blue regions are β-pleated sheets.
  - White regions are sections with no secondary structure.
  - White regions with a black box around them are disordered sections which were not determined by x-ray.

### Working with Surfaces
Protein surfaces can be mapped using presets which map different aspects of the protein. For example, the “Hydrophobic” color preset will calculate the molecular lipophilicity potential surface by recoloring the protein surface. With the Hydrophobic preset coloring, dark cyan represents the most hydrophilic surface and goldenrod represents the most lipophilic surface.
- To map surfaces, click on any of the presets in the **Coloring** section of the **Molecule Display** tab. Each button will display more information upon hover.
- To alter the transparency of visible surfaces, use the command `trans` and the percentage of the desired transparency. For example: `trans 50`
  - 0 equals no transparency and 100 equals full transparency
- Other useful commands when working with surfaces:
  - To show ligands, use the command `show ligand`
  - To hide the surface, use the command `surface hide`
  - To change the surface style, use the command `surface style` and the desired style. For example: `surface style mesh` or `surface style dot` or `surface style solid`
  - To change the surface color, use the command `surface color` and the name or hex code of the new color. For example: `surface color red` or `surface color #40526B`

### Deleting extra chains
At the top of the Log pane, chain information and non-standard residues information will be displayed. The letters underneath “Chain” in the Chain information panel indicate the number of chains. For example, a protein with Chain A, B, C, D, indicates that there are 4 chains, which the program refers to as “A”, “B,” etc. respectfully.
- Chains and non-standard residues can be selected by clicking on the chain names in the **Log** panel.
- ==**Deletion is permanent and cannot be undone.**== To delete chains, use the command `delete`, a forward slash (/), and the name of the chain to be deleted. For example: `delete /a` or `delete /d`
  - To delete multiple chains, use the command `delete`, a forward slash (/), and the names of the chains you want to delete separated by commas. For example: `delete /a,b,d`
  - It is also possible to delete a series of chains using commands in this format: `delete /a-d` and `delete /b-c`

## ChimeraX with VR
ChimeraX allows display and analysis of structures and density maps using virtual reality (VR) headsets. Its VR capabilities are still a work in progress and may not work exactly the same as the desktop mode. Visit ChimeraX’s page on VR at https://www.cgl.ucsf.edu/chimerax/docs/user/vr.html for more information.

### Opening VR
1. Open SteamVR then ChimeraX.
2. Open a protein model in ChimeraX.
3. In ChimeraX, use the command vr on
The VR headset will continue to function as the primary display until the command vr off is used.

### Basic Controls
- Move and rotate the model by holding the index finger trigger button on either controller, then moving the controller.
- Scale the model by holding the index finger trigger button on both controllers, then moving the controllers. Move the controllers together to shrink the model or move the controllers apart to make the model bigger.
- Show the VR user interface panel by pressing the B button on the left controller or the Y button on the right controller. In VR, the correct button will be marked with a rectangle on the cones representing the controllers.
  - Move the VR user interface by holding the same button and moving the controller.
- The buttons in the VR user interface panel can be clicked using the pointer finger trigger on the backside of the controller.
![Screenshot demonstrating the functions of the relevant buttons on the VR controllers. See information above.](https://raw.githubusercontent.com/OUETL/WorkflowDocumentation/main/chimerax%20screenshots/vr-controller-explained.png)
