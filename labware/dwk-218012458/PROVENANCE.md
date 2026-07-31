# DWK DURAN 218012458 — 100 mL GL45 Laboratory Bottle, Screw Cap + Pouring Ring

## Identity

- Manufacturer: DWK Life Sciences
- Product: DURAN Original GL 45 Laboratory Bottle, clear, with screw cap and pouring ring, PP, blue, 100 mL
- Catalog number: 218012458
- Source: https://www.dwk.com/duran-original-gl-45-laboratory-bottle-clear-with-screw-cap-and-pouring-ring-pp-blue-100-ml-218012458
- Cap source: https://www.dwk.com/duran-original-gl-45-laboratory-bottle-screw-cap-with-lip-seal-pp-blue-292392809

## Dimensions (manufacturer-published)

Capacity 100 mL, brim capacity 138 mL, diameter 56 mm, capped height 105 mm,
GL 45 thread (ISO 4796-1:2016 / DIN 168-1).

## Provenance

Independently reconstructed by the Matterix team from publicly published catalog
dimensions and parametric reconstruction inputs. This is a parametric
reconstruction, not manufacturer CAD. The published envelope dimensions are hard
constraints; unpublished wall, shoulder, thread, cap, and pouring-ring parameters
are reconstruction choices and are not represented as manufacturer specifications.

This asset is not derived from, supplied by, or endorsed by DWK Life Sciences.
DWK, DURAN, GL 45, and catalog number 218012458 are used solely to identify the
modeled product. Geometry was authored by us from published dimensions and is
offered under whatever license the upstream Matterix_assets repository specifies.

## Geometry and assembly

Units: meters, Z-up. Two rigid bodies: `Bottle` (bottle plus pouring ring merged)
and `Cap` (separate). Each body is centered at its own bounding-box centroid.
`InterfaceFrames/BaseFrame` is on the bottle footprint. Both bodies carry a
`CapMateFrame` at the coincident 80 mm source assembly origin. The bodies are
connected by a `PhysicsFixedJoint` with mutual bottle-cap contact filtered; no
`PhysicsArticulationRootAPI` is authored.

The composed capped envelope is 105 mm, matching the published capped height.

## Validation summary

PASS: both body meshes resolve with cavity-aware `convexDecomposition` collision
(64 bottle hulls, 32 cap hulls); the fixed-joint and coincident mate frames pass
the capped static check; the joint/no-articulation runtime stability contract is
preserved; and the Matterix interaction smoke is run against the assembled asset.
The collision approximation is not an exact interior surface.
