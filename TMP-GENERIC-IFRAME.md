# IFRAMES?

## What doesn't work ?
### Why doesn't the current "custom domains" work?
Site scripts are injected on tab.navigation. An iframe is not a tab.

### Just add the iframe to the manifest as a default permission?
This works great for a new installation, but..
- Deautorises the whole extension because it adds permissions.
- Hardcoded url makes it non-generic.

### Use the discord-activity approach?
Honestly: I think it's ugly because:
- parent page url and iframe url are hardcoded.
- requires broad permissions: webNavigation listener on all windows and iframes everywhere.
- special button in the UI for a single site.


# options?

### Hardcoded alternative, halfway the discord-activity approach:
* Just add a button: "Authorise owlbear" that hardcodes to a single owlbear extension url and calls registerContentScripts

NO

## Chosen approach:
Owlbear rodeo is nothing special, it should be a general generic site, without hardcoded url's.

* registerContentScripts does not need special permissions and works for iframes and tabs.
* Use the current ui for custom domains
* Downside : slight change in the way generic scripts are loaded for old customm sites.

