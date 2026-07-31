# Falcon 352070 — 50 mL conical centrifuge tube

This payload is an authored, evidence-labelled reconstruction of the Corning /
Falcon 50 mL High Clarity PP Conical Centrifuge Tube with Flat Top Screw Cap,
catalog 352070. Product identity and the published envelope were checked
against the manufacturer catalog and drawing:

- Product: 50 mL nominal capacity; 29.72 mm tube OD; 115.8 mm assembled
  length; 31.5 mm thread OD; 34.75 mm cap OD; 16,000 ×g maximum RCF.
- Source: <https://ecatalog.corning.com/life-sciences/b2c/US/en/Liquid-Handling/Tubes%2C-Liquid-Handling/Centrifuge-Tubes/Falcon%C2%AE-Conical-Centrifuge-Tubes/p/352070>
- Drawing: <https://www.corning.com/catalog/cls/documents/drawings/LSR00042_Falcon_Conical_Tube_50mL_352070_352098.pdf>

The source materials describe a parametric reconstruction, not manufacturer CAD.
Matterix authored this runtime payload and does not claim affiliation with
Corning or Falcon. The public payload contains only the authored USD and local
runtime materials; source OBJ/GLB/STL bundles remain internal evidence.

## Runtime contract

- Stage units are metres and `Z` is up.
- The tube and cap are separate dynamic rigid bodies connected by one
  `PhysicsFixedJoint` at coincident `CapMateFrame` anchors. Mutual Tube↔Cap
  contact is filtered to avoid seam jitter. No `PhysicsArticulationRootAPI` is
  authored.
- Body meshes are bbox-centred. The composed cap-top envelope spans 115.8 mm,
  matching the published assembled length.
- Collision uses `convexDecomposition` proxies with 64 tube hulls and 32 cap
  hulls.

The fixed-joint assembly is intended for the same direct two-body runtime path
as the DURAN capped payloads. Matterix's generic `RigidObject` scene wrapper
currently requires one rigid body per entity; a capped-specific scene adapter
is therefore still pending for interaction-smoke qualification.

## License and attribution

Declared rights holder and licensor: Steven Zhang, solely to the extent that
copyright or similar rights exist in the licensed material and Steven Zhang
owns or has authority to license those rights.

This authored payload is licensed under the Creative Commons Attribution 4.0
International license (CC BY 4.0; SPDX: `CC-BY-4.0`):
https://creativecommons.org/licenses/by/4.0/legalcode

Required attribution: “Matterix Batch 1 rigid-labware assets — © 2026 Steven
Zhang, licensed under CC BY 4.0.” A reasonable equivalent may identify Steven
Zhang, link to CC BY 4.0, and indicate changes.

This license applies only to rights Steven Zhang has authority to license in
the authored geometry, USD, meshes, materials, frames, and metadata. It does
not license manufacturer pages, drawings, photographs, standards, names,
brands, trademarks, patents, trade dress, or other third-party rights. No
manufacturer endorsement or affiliation is claimed.
