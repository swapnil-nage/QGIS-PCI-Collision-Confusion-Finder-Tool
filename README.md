PCI Finder 1.7.0

Filtered Arrows layer (new in 1.7.0):
- The post-filter (distance / PCI / Cell ID) now drives the "PCI Finder - Filtered Arrows" layer
  exactly as it drives the cells layer: only arrows to the cells shown in the table are kept.
- The arrows layer now has full attributes: Source_Cell_ID, Source_PCI, Cell_ID, Feature_ID, PCI,
  PCI_Mod3, Distance_km, Role, Conflict_PCI - so it can also be filtered/queried natively in QGIS.
- The "Highlight filtered cells / arrows on map" checkbox now also shows/hides both temporary layers.
- Export Filtered Map writes the filtered arrows (with the new attributes) alongside the cells.

PCI Finder 1.6.0

Toolbar (three separate tool icons + Settings):
- Same PCI            : click a cell, highlights all cells with the same PCI.
- PCI Mod-3 Conflict  : asks for max distance (km), finds same Mod-3 cells within it.
- PCI Confusion       : asks for max periphery (km), reports PCIs occurring on 2+ cells.
Each tool opens its own setup dialog (layer, PCI column, Cell Identity column). The three
buttons are mutually exclusive; the same entries are also under Plugins > PCI Finder.
All results, filter, copy/export and map-export features are unchanged from 1.5.0.


QGIS 3.44.x plugin.

Features:
- Choose any polygon layer, PCI field and Cell Identity field.
- Same PCI mode: highlights clicked cell green and other same-PCI cells yellow.
- PCI Mod-3 conflict mode: asks for maximum distance in km and identifies same-mod-3 cells within that centroid distance.
- PCI Confusion mode: checks all cells within the configured periphery and reports PCI values occurring on two or more cells.
- PCI Confusion arrows are PCI-themed: cells having the same PCI use the same arrow color.
- Distance arrows run from the clicked polygon centroid to each result cell centroid.
- Distance labels use configurable Arial Bold text with a tight white halo and no annotation box or red anchor dot.
- Result table includes Cell Identity, Feature ID, PCI, PCI Mod-3, Distance, Role and Conflict Group.
- Copy Table and Export CSV export the currently displayed result table.
- Searches the complete selected layer, not only the visible map extent.
- Does not modify the underlying layer symbology.

Post-result filtering (Version 1.5.0):
- Distance: no filter, below/equal to a selected distance, or above/equal to a selected distance.
- PCI: enter a specific PCI for an exact PCI match.
- Cell Identity: Contains or Does not contain a supplied string; matching is case-insensitive.
- Filters are combined using AND logic.
- Apply Filter updates both the table and map.
- Clear Filter restores all identified results.
- Optional checkbox controls whether filtered target cells and arrows are highlighted on the map; the clicked/source cell remains green as the reference.
- Copy Table and Export CSV operate on the filtered table currently shown.
