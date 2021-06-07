# NVDA Community Add-ons metadata

The NVDA Add-ons organization website hosts community add-ons metadata in JSON (JavaScript Object Notation) format. The purpose of the metadata is to help people and tools obtain information on add-ons such as summary, author, and NVDA compatibility information.

## Add-ons metadata contents

Add-ons metadata consists of two dictionaries:

* active: records information on stable add-ons listed on community add-ons website.
* legacy: information on add-ons declared legacy either because features are part of NVDA or were declared legacy by add-on developers.

Each dictionary is composed of add-on metadata with add-on identifiers as keys (these identifiers refer to internal add-on name used by NVDA and denotes "name" field in the add-on manifest). Each entry consists of:

* Summary (string): the name of the add-on shown to users from Add-ons Manager and/or on community add-ons website.
* Author (string): name and contact information for add-on authors.
* Add-on key (string): a shorthand used as part of the download link for the add-on from community add-ons website, intended for use by tools such as Add-on Updater.
* Legacy reason (string, legacy add-ons only): a reason specifying why an add-on was marked as legacy.
* Minimum and last tested NVDA versions (tuple of three integers): minimum and last tested NVDA versions the add-on is compatible with.
* Minimum Windows version (string): the oldest Windows release the add-on is compatible with.

## Updating add-ons metadata

Add-ons metadata should be updated when:

*New add-ons are added to community add-ons website.
* Any metadata field contents have changed, including NVDA and Windows compatibility information.
* Add-ons are declared legacy and/or legacy add-ons are being maintained again.
* Add-ons are removed from community add-ons website, either requested by add-on developers and/or by the community due to security and other reasons.

The following procedure should be used by add-ons metadata maintainers:

1. For new add-ons, wait for basic add-on review to be completed.
2. Wait for changes to add-on files repository (https://github.com/nvaccess/addonFiles).
3. For new and existing add-ons, once changes are made to the add-on files repository, download the new and/or updated add-ons and take note of add-on manifest.
4. Update the add-ons metadata JSON file. For new add-ons, add them in alphabetical order; for existing add-ons, edit changed field contents; for removed add-ons, remove them from JSON file; for add-ons declared legacy, move them from "active" to "legacy" section and add a reason from the developer and/or the community; if a legacy add-on is being maintained again, move it from "legacy" to "active" section.
5. Commit and push changes.
