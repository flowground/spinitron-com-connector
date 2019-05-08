# ![LOGO](logo.png) Spinitron v2 **flow**ground Connector

## Description

A generated **flow**ground connector for the Spinitron v2 API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/spinitron.com/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:09+03:00

## API Description

Maximum limit is 200. Default limit is 20.

## Authorization

Supported authorization schemes:
- API Key
## Actions

### Get Personas

*Tags:* `Persona`

#### Input Parameters
* `name` - _optional_ - Filter by Persona name
* `count` - _optional_ - Amount of items to return
* `page` - _optional_ - Offset, used together with count
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Get Persona by id

*Tags:* `Persona`

#### Input Parameters
* `id` - _required_
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Returns playlists optionally filtered by {start} and/or {end} datetimes

> Get Playlists optionally filtered by a datetime range.<br/>
> Only past Playlists will be returned (with allowed tolerance equals 1 hour in future).<br/>
> <br/>
> Ordered chronologically from newest to oldest.

*Tags:* `Playlist`

#### Input Parameters
* `start` - _optional_ - The datetime starting from items must be returned. Maximum 1 hour in future.

* `end` - _optional_ - The ending datetime. Maximum 1 hour in future.

* `show_id` - _optional_ - Filter by show
* `count` - _optional_ - Amount of items to return
* `page` - _optional_ - Offset, used together with count
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Get a Playlist by id

> The response object represents the playlist specified by {id}.<br/>
> <br/>
> Status 404 is returned if a playlist with {id} does not exist or if it does but starts in the future (with allowed tolerance equals 1 hour in future).

*Tags:* `Playlist`

#### Input Parameters
* `id` - _required_
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Returns scheduled shows optionally filtered by {start} and/or {end} datetimes

> **Terminology**: Spinitron defines a *show* as a radio program. A show can have one or more *schedules*,<br/>
> each of which may specify either an *occurence* or a *repetition*, which represents a set of occurences.<br/>
> Thus scheduled shows have occurences that, for example, may be displayed in a calendar.<br/>
> <br/>
> In the response, `items` is an array of objects representing occurences of scheduled shows.<br/>
> <br/>
> You may optionally filter `items` to a datetime *range* by including in the request {start} and/or {end}<br/>
> parameters, both of which must be no more than one hour in the past. An occurence starting at {end} is<br/>
> included in the reponse.<br/>
> <br/>
> `itmes` can include occurences that begin *or* end within the filter range. A show that goes on air before<br/>
> {start} appears in `items` if it ends *after* but not *at* {start}. An occurence starting at or before {end}<br/>
> is included.<br/>
> <br/>
> If the request omits the {start} parameter, the server sets its value to the current time so that the filter<br/>
> range's start is always defined. If the request specifies {end} then the requested range is *bounded*,<br/>
> otherwise it is *unbounded*.<br/>
> <br/>
> For a bounded request, `items` includes *every* occurence of all shows occuring in the range. The only<br/>
> difference between objects in `items` representing a given show will be the `start` field value.<br/>
> <br/>
> For an unbounded request, `items` includes *only one* occurence per show, specifically, the<br/>
> next occurrence after {start} of all shows occuring after {start}.<br/>
> <br/>
> Use an unbounded request to get a straight list all shows. Use a bounded request to get a calendar/agenda<br/>
> of shows expanded into occurrences by thir shedules and repetitions.<br/>
> <br/>
> Objects in `items` are ordered first by `datetime` and then by `id`.

*Tags:* `Show`

#### Input Parameters
* `start` - _optional_ - The datetime starting from items must be returned. Maximum 1 hour in past.

* `end` - _optional_ - The ending datetime. Maximum 1 hour in past.

* `count` - _optional_ - Amount of items to return
* `page` - _optional_ - Offset, used together with count
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Get a Show by id

> The response object represents the next occurence of the show specified by {id}.<br/>
> <br/>
> Status 404 is returned if a show with {id} does not exist or if it does but all its scheduled occurences elapsed in the past.

*Tags:* `Show`

#### Input Parameters
* `id` - _required_
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Returns spins optionally filtered by {start} and/or {end} datetimes

> Get Spins optionally filtered by a datetime range. Only past Spins will be returned.

*Tags:* `Spin`

#### Input Parameters
* `start` - _optional_ - The datetime starting from items must be returned.

* `end` - _optional_ - The ending datetime.

* `playlist_id` - _optional_ - Filter by playlist
* `show_id` - _optional_ - Filter by show
* `count` - _optional_ - Amount of items to return
* `page` - _optional_ - Offset, used together with count
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

### Log a Spin

> An endpoint for automation systems to log spins into the spin table.

*Tags:* `Spin`

### Get a Spin by id

*Tags:* `Spin`

#### Input Parameters
* `id` - _required_
* `fields` - _optional_ - Allows to select only needed fields
* `expand` - _optional_ - Allows to select extra fields

## License

**flow**ground :- Telekom iPaaS / spinitron-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
