## Events [**Back**](./../README.md)

- When attaching data payloads to events (whether DOM events or something more proprietary like Backbone events), pass a hash instead of a raw value. This allows a subsequent contributor to add more data to the event payload without finding and updating every handler for the event.

```js
/**
 * bad
 */
$(this).trigger('listingUpdated', listing.id);

/**
 * good
 */
$(this).trigger('listingUpdated', { listingId: listing.id });

/**
 * Event
 */
$(this).on('listingUpdated', function (e, listingId) {
    /**
     * Actions of handling the event
     */
});

```
