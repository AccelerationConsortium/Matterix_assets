# DWK DURAN 218014459 — 500 mL GL45 bottle

This payload is an authored, evidence-labelled reconstruction of the DWK Life
Sciences DURAN Original GL45 laboratory bottle, clear, with blue PP screw cap
and pouring ring, catalog 218014459. Product identity and envelope dimensions
were checked against the manufacturer catalog:

- Product: 500 mL nominal capacity; 619 mL brim capacity; 86 mm diameter;
  181 mm capped height; GL45; ISO 4796-1:2016 / DIN 168-1.
- Source: <https://www.dwk.com/duran-original-gl-45-laboratory-bottle-clear-with-screw-cap-and-pouring-ring-pp-blue-500-ml-218014459>
- Cap source: <https://www.dwk.com/duran-original-gl-45-laboratory-bottle-screw-cap-with-lip-seal-pp-blue-292392809>

The source materials describe a parametric reconstruction, not manufacturer CAD.
Matterix authored this runtime payload and does not claim affiliation with DWK
Life Sciences. The public payload contains only the authored USD and local
runtime materials; source OBJ/GLB/STL bundles remain internal evidence.

## Runtime contract

- Stage units are metres and `Z` is up.
- The bottle body merges the pouring ring; the cap remains a separate dynamic
  rigid body.
- Bottle and cap are connected by one `PhysicsFixedJoint` at coincident
  `CapMateFrame` anchors. Mutual bottle↔cap contact is filtered to avoid seam
  jitter. No `PhysicsArticulationRootAPI` is authored.
- Body meshes are bbox-centred. The composed body spans 176 mm and the cap-top
  envelope spans 181 mm, matching the published capped height.
- Collision uses cavity-preserving `convexDecomposition` proxies with 64 bottle
  hulls and 32 cap hulls.

The fixed-joint assembly passed the direct Isaac Sim two-body rest-stability
probe for 480 steps: relative origin error was 0 m and relative rotation error
was 0 degrees. Matterix's generic `RigidObject` scene wrapper currently
requires one rigid body per entity, so the capped multi-body assembly is kept
on the direct two-body runtime path pending a capped-specific scene adapter.

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
