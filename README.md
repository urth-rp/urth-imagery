# Urth Imagery

The map artwork pipeline for Urth Atlas.

It reads the official GIMP map sources (read-only — those files never move
and need no changes), exports the layers the Atlas displays — political
base, ocean, cities, subnational borders, and nation labels — and publishes
them where the Atlas picks them up automatically.

It runs every day, so official map updates reach the Atlas on their own,
plus a manual run button for re-runs. The Atlas is notified after every
successful sync.
