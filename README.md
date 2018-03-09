# Expirable activities extension idea

## Problem

There are several cases when an activity is done, but its validity will expire at some point in the future, possibly to be replaced with another activity of the same type.

Examples:

### Undertook First Aid training.

This training may be valid for 1 year after that it would need to be renewed. A new activity would be added when the person did the course again to keep their certification and the old one would be important to keep, but the latest one is the one that counts. The original activity has expired.

### Gave specific consent (as defined in GDPR).

An organisation may decide that after 2 years consent must be renewed. A contact could have lots of consent activities as they constantly renew their consent at each interaction. Only the latest consent is active; the others are marked expired since they are superseded.

### Group is running Fossil Free campaign.

An organisation may maintain an activity on -say- a campaign group’s record where they record the current state of how that group is getting on with the campaign. E.g. if you were the awesome and inspiring organisation [People & Planet](https://peopleandplanet.org/donate), calling for universities to divest from fossil fuels, you might have an activity that records what stage of the campaign the group is at and update this through the year. These activities can be summarised to show how many campaigns are running. At the end of the year you want to start with a new activity for that year and the old one kept for historical record.

**I have found myself implementing something like this time and again both in CiviCRM and other systems. So I thought I’d see whether it would be a good case for an extension.**

## How it might work

- Adds ‘expired’ to activity statuses list.
- Adds ‘expiry date’ custom field.
- Configuration allows you to select which activity types use the expiry date, and the default expiry (e.g. 2 years from creation).
- Cron job expires activities on or past expiry date.
- ?? Configuration allows you to select which activity types should trigger expiry of all previous activities of that type when a new one is added.
- ?? Report to find activities nearing their expiry date? E.g. identify staff who should be booked on that first aid course again within the next 2 months.

