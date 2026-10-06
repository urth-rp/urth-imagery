# Urth Imagery

Adapter for Urth XCF file sync and exports to Urth Atlas.

It reads the official map files, exports selected layers — political
base, ocean, cities, subnational borders, and subnational labels — and publishes
them then Urth Atlas picks them up automatically.

It runs every day, so official map updates reach the Atlas on their own,
plus, a manual run button for re-runs. Then Urth Atlas is notified after every
successful sync.
