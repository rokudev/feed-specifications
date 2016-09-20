# Direct Publisher Feed (JSON)

This guide includes detailed information on the Direct Publisher Feed Specification, which can be used to build a content feed that includes movies, series, TV Specials, and/or short-form videos.

Initially, a JSON format will be supported that follows the JSON-Schema Draft 4. All the properties in the schema are **case sensitive**.

Before submitting a feed, make sure it is a valid JSON file. You can easily do that by using an IDE, or free online tools like [JSON Scheme Validator](http://www.jsonschemavalidator.net/) or [JSON Schema Linter](http://jsonschemalint.com/draft4/).

# Direct Publisher Feed Schema
These are the properties for the root object of your feed. It contains basic information such as your company's name, when the feed was last updated, and other objects that will describe all your content such as TV Shows, Movies, etc.

<table class="c32"><tbody><tr class="c5"><td class="c26 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c48 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c78 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c36 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">providerName</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c78" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c36" colspan="1" rowspan="1"><p class="c64 c0 c47"><span class="c4">The name of the feed provider. E.g.: “Acme Productions”.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">lastUpdated</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c78 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c36 c31" colspan="1" rowspan="1"><p class="c0 c47 c64"><span class="c34">The date that the feed was last modified in the </span><span class="c8"><a class="c23" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1467923037560000&amp;usg=AFQjCNGTdVom4MH1mqtE-95T3jQDGANITw">ISO 8601</a></span><span class="c34">&nbsp;format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: </span><span class="c4">2015-11-11T22:21:37+00:00</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">language</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c78" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c36" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c34">The language the channel uses for all its information and descriptions. (e.g., “en”, “en-US”, “es”, etc.). </span><span class="c34">ISO 639 alpha-2 or alpha-3 language code string.</span></p></td></tr><tr class="c5"><td class="c117 c41" colspan="4" rowspan="1"><p class="c20 c37 c0"><span class="c81 c11">* At least one of the following is required.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c34">movies</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#movie">Movie Object</a></span><span class="c1">]</span></p></td><td class="c78 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c36 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">A list of one or more movies.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c34">series</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.m79l2gjp4m4t">Series Object</a></span><span class="c1">]</span></p></td><td class="c78" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c36" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">A list of one or more series. Series are episodic in nature and would include TV shows, daily/weekly shows, etc.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c34">shortFormVideos</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.lo963h5qynpi">ShortFormVideo Object</a></span><span class="c1">]</span></p></td><td class="c78 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c36 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">A list of one or more short-form videos. Short-form videos are usually less than 20 minutes long and are not TV Shows or Movies.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">tvSpecials</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.9pz21cidy6dg">TV Special Object</a></span><span class="c1">]</span></p></td><td class="c78" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c36" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">A list of one or more TV Specials. TV Specials are one-time TV programs that are not part of a series.</span></p><p class="c7 c0 c115"><span class="c4">&nbsp;</span></p></td></tr><tr class="c5"><td class="c117 c41" colspan="4" rowspan="1"><p class="c20 c37 c0 c17"><span class="c81 c11"></span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">categories</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.t5ygvbnie2m9">Category Object</a></span><span class="c1">]</span></p></td><td class="c78 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c36 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">An </span><span class="c11">ordered</span><span class="c4">&nbsp;list of one or more categories that will show up in your Roku Channel. Categories may also be manually specified within the Channel Builder if you do not want to provide them directly in the feed. Each time the feed is updated it will refresh the categories.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c4">playlists</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.y9g1embf3m7x">Playlist Object</a></span><span class="c1">]</span></p></td><td class="c78" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c36" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A list of one or more playlists.</span><span class="c34">&nbsp;They are useful for creating </span><span class="c11">manually ordered</span><span class="c4">&nbsp;categories inside your channel.</span></p></td></tr></tbody></table>

Direct Publisher Feed Root Object Example:

```json
{
    "providerName": "Acme Productions",
    "lastUpdated": "2015-11-11T22:21:37+00:00",
    "language": "en",
    "categories": [
        ...
    ],
    "playlists": [
        ...
    ],
    "movies": [
        ...
    ],
    "series": [
        ...
    ],
    "shortFormVideos":  [
        ...
    ],
    "tvSpecials": [
        ...
    ]
}
```

***
## movie
Child object of root property `movies`.

This object represents a movie object.

<table class="c32"><tbody><tr class="c5"><td class="c55 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c48 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c25 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c43 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">id</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">Your immutable string reference ID for the movie. </span><span class="c11">THIS CANNOT CHANGE</span><span class="c11">.</span><span class="c4">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">title</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Movie title. We use this value for matching in Roku Search. Please use plain text and don’t include extra information like year, version label, etc.</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">content</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.gemen2suvdxi">Content Object</a></span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The actual video content, such as the URL of the video file, subtitles, etc.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">genres</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The genre(s) of the movie. Must be one of the genres listed in the </span><span class="c8"><a class="c23" href="/roku-feed-supported-genres/">Direct Publisher Feed - Supported Genres</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">thumbnail</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The URL of the thumbnail for the movie. This is used within your channel and in search results.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c34">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio)</span><span class="c4">.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">releaseDate</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The date the movie was initially released or first aired</span><span class="c34">. </span><span class="c34">Used to sort programs chronologically and grouping related content in Roku Search. Conforms to the </span><span class="c8"><a class="c23" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1467923037699000&amp;usg=AFQjCNEzh0r7zrujHq0Wx5vfDmyEbgQm0A">ISO 8601</a></span><span class="c4">&nbsp;format: {YYYY}-{MM}-{DD}. E.g.: 2015-11-11</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">shortDescription</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c0 c20"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A movie description that </span><span class="c11">does not exceed 200 characters</span><span class="c4">. The text will be clipped if longer.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">longDescription</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A longer movie description that </span><span class="c11">does not exceed 500 characters</span><span class="c4">. The text will be clipped if longer. Must be different from shortDescription.</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">tags</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">One or more tags (e.g., “dramas”, “korean”, etc.). Each tag is a string and is limited to 20 characters. Tags are used to define what content will be shown within a </span><span class="c8"><a class="c23" href="#h.t5ygvbnie2m9">category</a></span><span class="c4">.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">extras</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5ffra02uupys">Extra Object</a></span><span class="c1">]</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more extras. Extras are additional content related to the movie, such as trailers and clips.</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">credits</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.htnvpx3uz3v">Credit Object</a></span><span class="c1">]</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more credits. The cast and crew of the movie.</span></p></td></tr><tr class="c5"><td class="c55 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">rating</span></p></td><td class="c48 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.q6t75zx5b5bm">Rating Object</a></span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A parental rating for the content.</span></p></td></tr><tr class="c5"><td class="c55" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">externalIds</span></p></td><td class="c48" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5vzi1c6dv67w">External ID Object</a></span><span class="c1">]</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more third-party metadata provider IDs.</span></p></td></tr></tbody></table>

Movie Object Example:

```json
{
    "id": "1509428502952",
    "title": "Sample Movie",
    "content": {
        ...
    },
    "genres": [
        "drama",
        "comedy",
        "horror"
    ],
    "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
    "releaseDate": "2016-01-01",
    "shortDescription": "Incredible movie description",
    "longDescription": "Even more incredible and longer movie description",
    "tags": [
        "amazing",
        "drama",
        "comedy",
        "horror"
    ]
}
```

***
### extra
Child object of property `movie` -> `extras`.

This object represents additional content related to a movie, such as trailers and clips.

<table class="c32"><tbody><tr class="c5"><td class="c41 c114" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c41 c119" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c41 c120" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c41 c112" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c110" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">id</span></p></td><td class="c107" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c100" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c84" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c34">Your immutable string reference ID for the extra video. </span><span class="c11">THIS CANNOT CHANGE.</span><span class="c4">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c5"><td class="c110 c31" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">content</span></p></td><td class="c107 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.gemen2suvdxi">Content Object</a></span></p></td><td class="c31 c100" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c84 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The actual video content, such as the URL of the video file, subtitles, etc.</span></p></td></tr><tr class="c5"><td class="c110" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c34">externalIds</span></p></td><td class="c107" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5vzi1c6dv67w">External ID Object</a></span><span class="c1">]</span></p></td><td class="c100" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c84" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more third-party metadata provider IDs.</span></p></td></tr></tbody></table>

***
## series
Child object of root property `series`.

This object represents a series, such as a season of a TV Show or a mini-series.

<table class="c32"><tbody><tr class="c5"><td class="c35" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c41 c127" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c41 c65" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c41 c138" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">id</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">Your immutable string reference ID for the series. </span><span class="c11">THIS CANNOT CHANGE.</span><span class="c4">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">title</span></p></td><td class="c46 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c31 c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The title of the series. </span><span class="c34">We use this field for matching</span><span class="c4">&nbsp;in Roku Search.</span></p></td></tr><tr class="c5"><td class="c118" colspan="4" rowspan="1"><p class="c20 c37 c0"><span class="c81 c11 c135">*Exactly one of the following is required</span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c34">seasons</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.vg4k6n88p4jh">Season Object</a></span><span class="c1">]</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more seasons of the series. Seasons should be used if episodes are grouped by seasons.</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">episodes</span></p></td><td class="c31 c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.ul2fscai6a1i">Episode Object</a></span><span class="c1">]</span></p></td><td class="c125 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more episodes of the series. Episodes should be used if they are not grouped by seasons (e.g., a mini-series).</span></p></td></tr><tr class="c5"><td class="c118" colspan="4" rowspan="1"><p class="c20 c37 c0 c17"><span class="c81 c11 c135"></span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c51 c0 c47 c63"><span class="c4">genres</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0 c101"><span class="c34">The genre(s) of the series. Must be one of the genres listed in the </span><span class="c8"><a class="c23" href="/roku-feed-supported-genres/">Direct Publisher Feed - Supported Genres</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c63 c51 c0 c47"><span class="c4">thumbnail</span></p></td><td class="c46 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c125 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The URL of the thumbnail for the series. This is used within your channel and in search results.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c34">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio).</span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">releaseDate</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The date the series first aired. </span><span class="c34">Used to sort programs chronologically and grouping related content in Roku Search</span><span class="c34">.</span><span class="c34">&nbsp;Conforms to the </span><span class="c8"><a class="c23" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1467923037892000&amp;usg=AFQjCNEpvvFIrdEQhZadNcOGc63ZyMZYoA">ISO 8601</a></span><span class="c4">&nbsp;format: {YYYY}-{MM}-{DD}. E.g.: 2015-11-11</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">shortDescription</span></p></td><td class="c46 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c125 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A description of the series that </span><span class="c11">does not exceed 200 characters</span><span class="c4">. The text will be clipped if longer.</span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c7 c0 c51"><span class="c4">longDescription</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A longer movie description that</span><span class="c11">&nbsp;does not exceed 500 characters</span><span class="c4">. The text will be clipped if longer. Must be different from shortDescription.</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">tags</span></p></td><td class="c46 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c125 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">One or more tags (e.g., “dramas”, “korean”, etc.). Each tag is a string and is limited to 20 characters. Tags are used to define what content will be shown within a </span><span class="c8"><a class="c23" href="#h.t5ygvbnie2m9">category</a></span><span class="c4">.</span></p></td></tr><tr class="c5"><td class="c21" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c4">credits</span></p></td><td class="c46" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.htnvpx3uz3v">Credit Object</a></span><span class="c1">]</span></p></td><td class="c125" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c53" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more credits. The cast and crew of the series.</span></p></td></tr><tr class="c5"><td class="c21 c31" colspan="1" rowspan="1"><p class="c7 c51 c0"><span class="c34">externalIds</span></p></td><td class="c46 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5vzi1c6dv67w">External ID Object</a></span><span class="c1">]</span></p></td><td class="c125 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c53 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more third-party metadata provider IDs.</span></p></td></tr></tbody></table>

Series Object Example (seasons):

```json
{
  "id": "1509428502952",
  "title": "The Amazing Series with Seasons!",
  "seasons": [
    ...
  ],
  "genres": [
    "educational",
    "science fiction",
    "thriller",
  ],
  "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
  "shortDescription": "Wondrous series seasons."
}
```

Series Object Example (mini-series):

```json
{
  "id": "1509428502952",
  "title": "The Amazing Series with Episodes Only!",
  "episodes": [
    ...
  ],
  "genres": [
    "fashion",
    "romance",
    "technology",
  ],
  "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
  "shortDescription": "Unbelievables series episodes."
}
```

***
### season
Child object of property `series` -> `seasons`.

This object represents a single season of a series.

<table class="c32"><tbody><tr class="c5"><td class="c41 c144" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c41 c123" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c41 c146" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c41 c141" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c66" colspan="1" rowspan="1"><p class="c7 c61 c0"><span class="c4">seasonNumber</span></p></td><td class="c132" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">integer</span></p></td><td class="c82" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c103" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Sequential season number. E.g.: 3 or 2015.</span></p></td></tr><tr class="c5"><td class="c66 c31" colspan="1" rowspan="1"><p class="c7 c0 c61"><span class="c4">episodes</span></p></td><td class="c31 c132" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.ul2fscai6a1i">Episode Object</a></span><span class="c1">]</span></p></td><td class="c31 c82" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c103 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more episodes of this particular season.</span></p></td></tr><tr class="c5"><td class="c66" colspan="1" rowspan="1"><p class="c7 c61 c0"><span class="c4">thumbnail</span></p></td><td class="c132" colspan="1" rowspan="1"><p class="c20 c61 c0"><span class="c1">string</span></p></td><td class="c82" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c103" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The URL of the thumbnail for the season.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio).</span></p></td></tr></tbody></table>

Season Object Example:

```json
{
  "seasonNumber": "1",
  "episodes": [
    ...
  ]
}
```

***
### episode
Child object of property:

`series` -> `episodes`
`series` -> `seasons` -> `episodes`

This object represents a single episode in a series or a season.

<table class="c32"><tbody><tr class="c5"><td class="c41 c50" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c62 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c77 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c43 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">id</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">Your immutable string reference ID for the episode. </span><span class="c11">THIS CANNOT CHANGE.</span><span class="c4">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c5"><td class="c50 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">title</span></p></td><td class="c62 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Episode title. We use this value for matching in Roku Search. Please don’t include extra information like year, version label, etc.</span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">content</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.gemen2suvdxi">Content Object</a></span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The actual video content, such as the URL of the video file, subtitles, etc.</span></p></td></tr><tr class="c5"><td class="c50 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">thumbnail</span></p></td><td class="c62 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The URL of the thumbnail for the episode. This is used within your channel and in search results.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio).</span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">episodeNumber</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">integer</span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c0 c7"><span class="c4">The sequential episode number. E.g.: 3.</span></p></td></tr><tr class="c5"><td class="c50 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">releaseDate</span></p></td><td class="c31 c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The date the episode first aired. Used to sort programs chronologically and grouping related content in Roku Search. Conforms to the </span><span class="c8"><a class="c23" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1467923038055000&amp;usg=AFQjCNEhej9IeToJXFjzQHmwjTvwjMgC9A">ISO 8601</a></span><span class="c4">&nbsp;format: {YYYY}-{MM}-{DD}. E.g.: 2015-11-11</span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">shortDescription</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">An episode description that </span><span class="c11">does not exceed 200 characters</span><span class="c4">. The text will be clipped if longer.</span></p></td></tr><tr class="c5"><td class="c50 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">longDescription</span></p></td><td class="c62 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c77 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A longer episode description that </span><span class="c11">does not exceed 500 characters</span><span class="c4">. The text will be clipped if longer. Must be different from shortDescription.</span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">credits</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.htnvpx3uz3v">Credit Object</a></span><span class="c1">]</span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more credits. The cast and crew of the episode.</span></p></td></tr><tr class="c5"><td class="c50 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">rating</span></p></td><td class="c62 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.q6t75zx5b5bm">Rating Object</a></span></p></td><td class="c77 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A parental rating for the content.</span></p></td></tr><tr class="c5"><td class="c50" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">externalIds</span></p></td><td class="c62" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5vzi1c6dv67w">External ID Object</a></span><span class="c1">]</span></p></td><td class="c77" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more third-party metadata provider IDs.</span></p></td></tr></tbody></table>

Episode Object Example:

```json
{
  "id": "1509428502952",
  "title": "The Amazing First Episode Title",
  "content": {
    ...
  },
  "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
  "episodeNumber": 1,
  "shortDescription": "Marvelous episode description"
}
```

***
## shortFormVideo
Child object of root property `shortFormVideos`.

Short-form videos are generally less than 20 minutes long, and are not TV Shows or Movies.

<table class="c57"><tbody><tr class="c14"><td class="c97 c84" colspan="1" rowspan="1"><p class="c10 c2 c35"><span class="c13 c33">Field</span></p></td><td class="c127 c84" colspan="1" rowspan="1"><p class="c32 c2"><span class="c26 c13">Type</span></p></td><td class="c75 c84" colspan="1" rowspan="1"><p class="c32 c2"><span class="c13 c33">Required </span></p></td><td class="c9 c84" colspan="1" rowspan="1"><p class="c10 c2 c54"><span class="c13 c33">Description </span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">id</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required </span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">Your immutable string reference ID for the video. </span><span class="c13 c33">THIS CANNOT CHANGE.</span><span class="c0">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c14"><td class="c97 c39" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">title</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c11" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required</span></p></td><td class="c9 c39" colspan="1" rowspan="1"><p class="c10 c2"><span class="c0">Video title. We use this value for matching in Roku Search. Please don’t include extra information like year, version label, etc.</span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">content</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c5"><a class="c20" href="#h.gemen2suvdxi">Content Object</a></span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required</span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c0">The actual video content, such as the URL of the video file, subtitles, etc.</span></p></td></tr><tr class="c14"><td class="c97 c39" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">thumbnail</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c11" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required</span></p></td><td class="c9 c39" colspan="1" rowspan="1"><p class="c10 c2"><span class="c0">The URL of the thumbnail for the video. This is used within your channel and in search results.</span></p><p class="c10 c2 c18"><span class="c0"></span></p><p class="c10 c2"><span class="c0">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio). </span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">shortDescription</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required</span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">A description of the video that </span><span class="c13 c33">does not exceed 200 characters</span><span class="c0">. The text will be clipped if longer.</span></p></td></tr><tr class="c14"><td class="c97 c39" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">releaseDate</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c11" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Required</span></p></td><td class="c9 c39" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">The date the video first became available. </span><span class="c13">Used to sort programs chronologically and grouping related content in Roku Search.</span><span class="c13">&nbsp;Optional but very important, we recommend that you provide this. </span><span class="c13">Conforms to the </span><span class="c13 c62 c79"><a class="c20" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1470958584357000&amp;usg=AFQjCNHhJVoDwV5zcHShnjusvB2MdRoE3g">ISO 8601</a></span><span class="c0">&nbsp;format: {YYYY}-{MM}-{DD}. E.g.: 2015-11-11</span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">longDescription</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">string</span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Optional</span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">A longer description that </span><span class="c13 c33">does not exceed 500 characters</span><span class="c0">. The text will be clipped if longer. Must be different from shortDescription.</span></p></td></tr><tr class="c14"><td class="c97 c39" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">tags</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c32 c2"><span class="c8">[string]</span></p></td><td class="c11" colspan="1" rowspan="1"><p class="c32 c2"><span class="c13">Optional</span></p></td><td class="c9 c39" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">One or more tags (e.g., “dramas”, “korean”, etc). Each tag is a string and is limited to 20 characters. Tags are used to define what content will be shown within a </span><span class="c13 c62 c79"><a class="c20" href="#h.t5ygvbnie2m9">category</a></span><span class="c0">.</span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">genres</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c22 c8">[string]</span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Optional</span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">The genre(s) of the video. Must be one of the genres listed in </span><span class="c13 c62 c79"><a class="c20" href="#h.nc6hui6dfxnv">Appendix B</a></span><span class="c0">.</span></p></td></tr><tr class="c14"><td class="c97 c39" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">credits</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c32 c2"><span class="c8">[</span><span class="c5"><a class="c20" href="#h.htnvpx3uz3v">Credit Object</a></span><span class="c22 c8">]</span></p></td><td class="c11" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Optional</span></p></td><td class="c9 c39" colspan="1" rowspan="1"><p class="c10 c2"><span class="c0">One or more credits. The cast and crew of the video.</span></p></td></tr><tr class="c14"><td class="c97" colspan="1" rowspan="1"><p class="c7 c2"><span class="c0">rating</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c32 c2"><span class="c5"><a class="c20" href="#h.q6t75zx5b5bm">Rating Object</a></span></p></td><td class="c75" colspan="1" rowspan="1"><p class="c32 c2"><span class="c0">Optional</span></p></td><td class="c9" colspan="1" rowspan="1"><p class="c10 c2"><span class="c13">A parental rating for the content.</span></p></td></tr></tbody></table>

Short-form Video Object Example:

```json
{
  "id": "1509428502952",
  "title": "The Amazing Short-form Video",
  "content": {
    ...
  },
  "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
  "shortDescription": "Astonishing short-form video"
  "releaseDate": "2016-01-01"
}
```

***
## tvSpecial
Child object of root property `tvSpecials`.

<table class="c32"><tbody><tr class="c5"><td class="c26 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c22 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c83 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c41 c43" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">id</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">Your immutable string reference ID for the TV Special. </span><span class="c11">THIS CANNOT CHANGE.</span><span class="c4">&nbsp;This should serve as a unique identifier for the movie across different locales.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">title</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Episode title. We use this value for matching in Roku Search. Please don’t include extra information like year, version label, etc.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">content</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.gemen2suvdxi">Content Object</a></span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The actual video content, such as the URL of the video file, subtitles, etc.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">thumbnail</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The URL of the thumbnail for the TV Special. This is used within your channel and in search results.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">Image dimensions must be at least 800x450 (width x height, 16x9 aspect ratio).</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">genres</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The genre(s) of the movie. Must be one of the genres listed in the </span><span class="c8"><a class="c23" href="/roku-feed-supported-genres/">Rou Feed - Support Genres</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">releaseDate</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The date the TV Special first aired. Used to sort programs chronologically and grouping related content in Roku Search.</span><span class="c34">&nbsp;</span><span class="c34">Conforms to the </span><span class="c8"><a class="c23" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1467923038192000&amp;usg=AFQjCNFTvif_ZhdsBLOifw0yhJjLD5mWxw">ISO 8601</a></span><span class="c4">&nbsp;format: {YYYY}-{MM}-{DD}. E.g.: 2015-11-11</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">shortDescription</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A description of the special that </span><span class="c11">does not exceed 200 characters</span><span class="c4">. The text will be clipped if longer.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">longDescription</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c83 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A longer episode description that </span><span class="c11">does not exceed 500 characters</span><span class="c4">. The text will be clipped if longer. Must be different from shortDescription.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">credits</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.htnvpx3uz3v">Credit Object</a></span><span class="c1">]</span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more credits. The cast and crew of the TV special.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">rating</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c10 c33"><a class="c23" href="#h.q6t75zx5b5bm">Rating Object</a></span></p></td><td class="c31 c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">A parental rating for the content.</span></p></td></tr><tr class="c5"><td class="c26" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">tags</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c83" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c43" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">One or more tags (e.g., “dramas”, “korean”, etc). Each tag is a string and is limited to 20 characters. Tags are used to define what content will be shown within a </span><span class="c8"><a class="c23" href="#h.t5ygvbnie2m9">category</a></span><span class="c4">.</span></p></td></tr><tr class="c5"><td class="c26 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">externalIds</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c33">[</span><span class="c10 c33"><a class="c23" href="#h.5vzi1c6dv67w">External ID Object</a></span><span class="c1">]</span></p></td><td class="c83 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Optional</span></p></td><td class="c30" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">One or more third-party metadata provider IDs.</span></p></td></tr></tbody></table>

TV Special Object Example:

```json
{
  "id": "1509428502952",
  "title": "The Amazing First Episode Title",
  "content": {
    ...
  },
  "genres": [
    "animals",
    "animated",
    "fantasy",
  ],
  "thumbnail": "https://example.org/cdn/thumbnails/1509428502952/1",
  "shortDescription": "Unusual episode description"
}
```

***
## category
Child object of root property `categories`.

The category object defines a new category your channel will display, and the content included in it based either on a playlist (see object description below), or a query containing one or multiple tags. You can also create them directly in the Channel Builder.

There are three default categories in every channel: "Continue Watching", "Most Popular", and "Recently Added".

Each category is displayed as a separate row to end-users.

<table class="c32"><tbody><tr class="c5"><td class="c40 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c56 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c96 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c12 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c40" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">name</span></p></td><td class="c56" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c96" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c12" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The name of the category that will show up in the channel.</span></p></td></tr><tr class="c5"><td class="c41 c117" colspan="4" rowspan="1"><p class="c20 c37 c0"><span class="c81 c11">* Exactly one of the following is required</span></p></td></tr><tr class="c5"><td class="c31 c40" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">playlistName</span></p></td><td class="c56 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c96 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c12 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The name of the playlist in this feed that contains the content for this category.</span></p></td></tr><tr class="c5"><td class="c40" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">query</span></p></td><td class="c56" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c96" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required*</span></p></td><td class="c12" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The query that will specify the content for this category. It is a </span><span class="c34">Boolean expression</span><span class="c4">&nbsp;containing tags that you have provided in your content feed. The available operators are:</span></p><ul class="c28 lst-kix_tushb9adfn5-0 start"><li class="c7 c49 c0"><span class="c4">AND</span></li><li class="c7 c49 c0"><span class="c4">OR</span></li></ul><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">You cannot use both of them in the same query. You can use more than one.</span></p><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">&nbsp;For example, if your feed has the tags "romance", "movie", "korean" and "dramas", you could do:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_c6blfk73nk6m-0 start"><li class="c7 c49 c0"><span class="c34">m</span><span class="c4">ovie AND korean</span></li><li class="c7 c49 c0"><span class="c34">m</span><span class="c4">ovie AND korean AND dramas</span></li><li class="c7 c49 c0"><span class="c34">r</span><span class="c4">omance OR dramas</span></li></ul><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c34">The following is </span><span class="c11">NOT</span><span class="c4">&nbsp;supported:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_8lnzp0moe102-0 start"><li class="c7 c49 c0"><span class="c34">m</span><span class="c4">ovie AND romance OR dramas</span></li></ul><p class="c7 c0 c17"><span class="c4"></span></p></td></tr><tr class="c5"><td class="c117 c41" colspan="4" rowspan="1"><p class="c20 c37 c0 c17"><span class="c81 c11 c135"></span></p></td></tr><tr class="c5"><td class="c40 c31" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">order</span></p></td><td class="c31 c56" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c96 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c12 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">The order of the category. Must be one of the following:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_5r2h06splk9d-0 start"><li class="c7 c49 c0"><span class="c4">manual – For playlists only</span></li><li class="c7 c49 c0"><span class="c4">most_recent – reverse chronological order</span></li><li class="c7 c49 c0"><span class="c4">chronological – the order in which the content was published (e.g., Episode 1, Episode 2, etc.)</span></li><li class="c7 c49 c0"><span class="c4">most_popular – sort by popularity (based on Roku usage data).</span></li></ul></td></tr></tbody></table>

Category Object Example (query):

```json
{
    "name": "Cooking Shows",
    "query": "cooking AND reality shows",
    "order": "most_popular"
}
```

Category Object Example (playlist):

```json
{
    "name": "Featured",
    "playlistName": "featured content",
    "order": "manual"
}
```

***
## playlist
Child object of root property `playlists`.

A playlist is an **ordered** list of videos that may contain a mix of Movies, Series, Short-form videos, and TV Specials. It references a list of video IDs that are defined elsewhere in the feed. The same video can be referenced in multiple playlists.

Playlists are similar to tags: they help you define the content which your channel's categories will display. The main difference is that playlists let you manually specify the order of the content, and so they are perfect, for example, to create a "Featured" category in your channel.

<table class="c32"><tbody><tr class="c44"><td class="c131 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c25 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11 c81">Type</span></p></td><td class="c22 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c112 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c131" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">name</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c22" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c112" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The name of the playlist. The name is </span><span class="c11">limited to 20 characters</span><span class="c4">.</span></p></td></tr><tr class="c5"><td class="c131 c31" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">itemIds</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">[string]</span></p></td><td class="c3" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c112 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">An </span><span class="c11">ordered</span><span class="c4">&nbsp;list of one or more item IDs. An item ID is the ID of a movie/series/short-form video/TV special.</span></p><p class="c7 c0 c115"><span class="c4">&nbsp;</span></p></td></tr></tbody></table>

Playlist Object Example:

```json
{
    "name": "featured content",
    "itemIds": [
        "1509428502952",
        "1509428502953",
        "1509428502954"
    ]
}
```

***
## content
Child object of property:

* `movie`
* `movie` -> `extra`
* `series` -> `episodes` -> `episode`
* `series` -> `seasons` -> `episodes` -> `episode`
* `shortFormVideo`
* `tvSpecial`

This object represents the details about a single video content of a movie, episode, short-form video, or TV special.

<table class="c75"><tbody><tr class="c3"><td class="c71 c126" colspan="1" rowspan="1"><p class="c5 c56"><span class="c81 c46 c1">Field</span></p></td><td class="c71 c106" colspan="1" rowspan="1"><p class="c4"><span class="c63 c46 c1">Type</span></p></td><td class="c118 c71" colspan="1" rowspan="1"><p class="c4"><span class="c81 c46 c1">Required </span></p></td><td class="c64 c71" colspan="1" rowspan="1"><p class="c5 c84"><span class="c81 c46 c1">Description </span></p></td></tr><tr class="c3"><td class="c39" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">dateAdded</span></p></td><td class="c117" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">string</span></p></td><td class="c143" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Required</span></p></td><td class="c31" colspan="1" rowspan="1"><p class="c97 c33 c28"><span class="c46 c1">The date the video was added to the library in the </span><span class="c14 c46 c1"><a class="c16" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1468008705128000&amp;usg=AFQjCNGAgj35F7MdXCqfTdydZ4yxMXD69A">ISO 8601</a></span><span class="c13 c1">&nbsp;format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00</span></p><p class="c0"><span class="c13 c1"></span></p><p class="c5 c96"><span class="c13 c1">This information is used to generate the “Recently Added” category.</span></p></td></tr><tr class="c3"><td class="c39 c49" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">videos</span></p></td><td class="c117 c49" colspan="1" rowspan="1"><p class="c4"><span class="c12">[</span><span class="c14 c12"><a class="c16" href="#h.grtwkg3gbejq">Video Object</a></span><span class="c13 c17">]</span></p></td><td class="c143 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Required</span></p></td><td class="c31 c49" colspan="1" rowspan="1"><p class="c5 c96"><span class="c46 c1">One or more video files.</span><span class="c13 c1">&nbsp;For non-adaptive streams, you can specify the same video with different qualities so the Roku player can choose the best one based on bandwidth. </span></p></td></tr><tr class="c3"><td class="c39" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">duration</span></p></td><td class="c117" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">integer</span></p></td><td class="c143" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Required</span></p></td><td class="c31" colspan="1" rowspan="1"><p class="c5 c96"><span class="c13 c1">Runtime in seconds.</span></p></td></tr><tr class="c3"><td class="c39 c49" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">captions</span></p></td><td class="c117 c49" colspan="1" rowspan="1"><p class="c4"><span class="c12">[</span><span class="c14 c12"><a class="c16" href="#h.qnl7n8kmyqi6">Caption Object</a></span><span class="c13 c17">]</span></p></td><td class="c143 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Required*</span></p></td><td class="c31 c49" colspan="1" rowspan="1"><p class="c5 c96"><span class="c46 c1">One or more video caption files. This is </span><span class="c81 c46 c1">required except for short-form videos</span><span class="c46 c1">. &nbsp;Supported formats are described in the </span><span class="c14 c46 c1"><a class="c16" href="/closed-caption-subtitles-support/">Closed Caption / Subtitle Support</a></span><span class="c13 c1"> article.</span></p></td></tr><tr class="c3"><td class="c39" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">trickPlayFiles</span></p></td><td class="c117" colspan="1" rowspan="1"><p class="c4"><span class="c12">[</span><span class="c14 c12"><a class="c16" href="#h.fl71ymjzaesn">Trickplay File Object</a></span><span class="c13 c17">]</span></p></td><td class="c143" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Optional</span></p></td><td class="c31" colspan="1" rowspan="1"><p class="c5 c96"><span class="c13 c1">The trickplay file(s) that displays images as a user scrubs through a video, in Roku’s BIF format. Trickplay files in multiple qualities can be provided.</span></p></td></tr><tr class="c3"><td class="c39 c49" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">language</span></p></td><td class="c117 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">string</span></p></td><td class="c143 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Optional</span></p></td><td class="c31 c49" colspan="1" rowspan="1"><p class="c5 c96"><span class="c46 c1">The language in which the video was originally produced (e.g., “en”, “en-US”, “es”, etc). </span><span class="c46 c1">ISO 639 alpha-2 or alpha-3 language code string.</span></p></td></tr><tr class="c3"><td class="c39" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">validityPeriodStart</span></p></td><td class="c117" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">string</span></p></td><td class="c143" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Optional</span></p></td><td class="c31" colspan="1" rowspan="1"><p class="c97 c33 c28"><span class="c46 c1">The date when the content should become available in the </span><span class="c14 c46 c1"><a class="c16" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1468008705166000&amp;usg=AFQjCNHT_zs6OiG5cwyXQ3oWCOPwTVIcYw">ISO 8601</a></span><span class="c13 c1">&nbsp;format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00</span></p></td></tr><tr class="c3"><td class="c39 c49" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">validityPeriodEnd</span></p></td><td class="c117 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">string</span></p></td><td class="c143 c49" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Optional</span></p></td><td class="c31 c49" colspan="1" rowspan="1"><p class="c97 c33 c28"><span class="c46 c1">The date when the content is no longer available in the </span><span class="c14 c46 c1"><a class="c16" href="https://www.google.com/url?q=http://www.iso.org/iso/home/standards/iso8601.htm&amp;sa=D&amp;ust=1468008705173000&amp;usg=AFQjCNEvaSp0RyYRiEymawfu90xgSLUPMQ">ISO 8601</a></span><span class="c46 c1">&nbsp;format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00</span></p></td></tr><tr class="c3"><td class="c39" colspan="1" rowspan="1"><p class="c5 c67"><span class="c13 c1">adBreaks</span></p></td><td class="c117" colspan="1" rowspan="1"><p class="c4"><span class="c13 c17">[string]</span></p></td><td class="c143" colspan="1" rowspan="1"><p class="c4"><span class="c13 c1">Optional</span></p></td><td class="c31" colspan="1" rowspan="1"><p class="c97 c33 c28"><span class="c13 c1">One or more time codes. Represents a time duration from the beginning of the video where an ad shows up. Conforms to the format: {hh}:{mm}:{ss}.</span></p></td></tr></tbody></table>

Content Object Example:

```json
{
  "dateAdded": "2015-11-11T22:21:37+00:00",
  "videos": [
    ...
  ],
  "trickPlayFiles": [
    ...
  ],
  "duration": 1290
}
```

***
### video
Child object of property `content` -> `videos`.

This object represents the details of a single video file.

<table class="c32"><tbody><tr class="c5"><td class="c86 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c41 c69" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c22 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c113 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c45" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">url</span></p></td><td class="c74" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c104" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c60" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c34">The URL of the video itself. The video should be served from a CDN (Content Distribution Network). Supported formats are described in the </span><span class="c8"><a class="c23" href="/video-encoding-guidelines/">Video Encoding Guidelines</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c45 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">quality</span></p></td><td class="c74 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c31 c104" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c31 c60" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Must be one of the following:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_szb39u19sfsi-0 start"><li class="c7 c49 c0"><span class="c4">HD – 720p</span></li><li class="c7 c49 c0"><span class="c4">FHD – 1080p</span></li><li class="c7 c49 c0"><span class="c4">UHD – 4K</span></li></ul><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c4">If your stream uses an adaptive bitrate, set the quality to the highest available.</span></p></td></tr><tr class="c5"><td class="c45" colspan="1" rowspan="1"><p class="c7 c0 c14"><span class="c4">videoType</span></p></td><td class="c74" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c104" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c60" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c4">Must be one of the following:</span></p><p class="c7 c0 c79 c17"><span class="c4"></span></p><ul class="c28 lst-kix_cwuom24mfj77-0 start"><li class="c7 c49 c0 c79"><span class="c4">HLS</span></li><li class="c7 c49 c0 c79"><span class="c4">SMOOTH</span></li><li class="c7 c49 c0 c79"><span class="c4">DASH</span></li><li class="c7 c49 c0 c79"><span class="c4">MP4</span></li><li class="c7 c49 c0 c79"><span class="c4">MOV</span></li><li class="c7 c49 c0 c79"><span class="c34">M4V</span></li></ul></td></tr><tr class="c5"><td class="c31 c45" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">bitrate</span></p></td><td class="c31 c74" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">integer</span></p></td><td class="c104 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required only for non-ABR streams.</span></p></td><td class="c60 c31" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c4">The bitrate in kbps. For non-adaptive streams, this must be provided. It is not needed for an ABR (e.g., HLS) stream.</span></p></td></tr></tbody></table>

Video Object Example:

```json
{
  "url": "https://example.org/cdn/videos/1509428502952",
  "quality": "UHD",
  "videoType": "HLS"
}
```

***
### caption
Child object of property `content` -> `captions`.

This object represents a single video caption file of a video content. The supported formats are described in the [Closed Caption / Subtitle Support](/closed-caption-subtitles-support/) article.

<table class="c32"><tbody><tr class="c5"><td class="c133 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c85 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c25 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c12 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c133" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">url</span></p></td><td class="c85" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c12" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The URL of the video caption file. Supported formats are described in the </span><span class="c8"><a class="c23" href="/closed-caption-subtitles-support/">Closed Caption / Subtitle Support</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c133 c31" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">language</span></p></td><td class="c85 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c25 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c12 c31" colspan="1" rowspan="1"><p class="c7 c0 c79"><span class="c34">A language code for the subtitle (e.g., “en”, “es-mx”, “fr”, etc). </span><span class="c34">ISO 639 alpha-2 or alpha-3 language code string.</span><sup><a href="#cmnt3" id="cmnt_ref3">[c]</a></sup></p></td></tr><tr class="c5"><td class="c133" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">captionType</span></p></td><td class="c85" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c25" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c12" colspan="1" rowspan="1"><p class="c134 c0 c47"><span class="c4">A string specifying the type of caption. Default is subtitle. Must be one of the following:</span></p><p class="c134 c0 c17 c47"><span class="c4"></span></p><ul class="c28 lst-kix_hxye7gifnt62-0 start"><li class="c134 c49 c0 c47"><span class="c4">CLOSED_CAPTION</span></li><li class="c49 c0 c47 c134"><span class="c34">SUBTITLE</span><sup><a href="#cmnt4" id="cmnt_ref4">[d]</a></sup></li></ul></td></tr></tbody></table>

Caption File Object Example:

```json
{
  "url": "https://example.org/cdn/subtitles/1509428502952/sub-fr.srt",
  "Language": "fr",
  "captionType": "CLOSED_CAPTION"
}
```

***
### trickPlayFile
Child object of property `content` -> `trickPlayFiles`.

This object represents a single trickplay file. Trickplay files are the images shown when a user scrubs through a video, either fast-forwarding or rewinding. The file must be in the Roku BIF format, as described in the [Trick Mode Support](/trick-mode-support/) article.

<table class="c32"><tbody><tr class="c5"><td class="c41 c52" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c85 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c127 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c122 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c52" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">url</span></p></td><td class="c85" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c127" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c122" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The URL to the image representing the trickplay file Must be in the Roku BIF format, more information in the </span><span class="c8"><a class="c23" href="/trick-mode-support/">Trick Mode Support</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c52 c31" colspan="1" rowspan="1"><p class="c7 c0 c39"><span class="c4">quality</span></p></td><td class="c85 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c127 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c31 c122" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Must be one of the following:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_edm1h2nezgr9-0 start"><li class="c7 c49 c0"><span class="c4">HD – 720p</span></li><li class="c7 c49 c0"><span class="c4">FHD – 1080p</span></li></ul></td></tr></tbody></table>

Trickplay File Object Example:

```json
{
  "url": "https://example.org/cdn/trickplayFiles/1509428502952/1",
  "quality": "FHD"
}
```

***
## externalId
Child object of property:

* `movie`
* `movie` -> `extras` -> `extra`
* `series`
* `series` -> `episodes` -> `episode`
* `series` -> `seasons` -> `episodes` -> `episode`
* `shortFormVideo`
* `tvSpecial`

This object represents a third-party metadata provider ID (such as TMS, Rovi, IMDB, EIDR), that can provide more information about a specific video content. This information is used to optimize your content to be discovered within the Roku Search, and provide more details to users.

<table class="c32"><tbody><tr class="c5"><td class="c86 c41" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c128 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c89 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c41 c113" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c86" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">id</span></p></td><td class="c128" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">string</span></p></td><td class="c89" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required </span></p></td><td class="c113" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">The third-party metadata provider ID for your video content. For example, in the case of IMDB you would use the last part of the URL of a movie such as "http://www.imdb.com/title/</span><span class="c11">tt0371724</span><span class="c34">/".</span></p></td></tr><tr class="c5"><td class="c86 c31" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">idType</span></p></td><td class="c31 c128" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c31 c89" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c29" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Must be one of the following:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_zh0843rgifgc-0 start"><li class="c7 c49 c0"><span class="c4">TMS – A Tribune Metadata Service ID for the content</span></li><li class="c7 c49 c0"><span class="c4">ROVI - A Rovi ID for the content</span></li><li class="c7 c49 c0"><span class="c4">IMDB – An Internet Movie Database ID.</span></li><li class="c7 c49 c0"><span class="c4">EIDR – An Entertainment Identifier Registry ID </span></li></ul></td></tr></tbody></table>

External ID Object Example:

```json
{
  "id": "tt0371724",
  "idType": "IMDB"
}
```

***
## rating
Child object of property:

`movie`
`series` -> `episodes` -> `episode`
`shortFormVideo`
`tvSpecial`

This object represents the rating for the video content. You can define the parental rating, as well as the source (USA Parental Rating, UK Content Provider, etc). Check the [Direct Publisher Feed - Parental Ratings](/roku-feed-parental-ratings/) article for all the acceptable parental ratings values.

<table class="c32"><tbody><tr class="c5"><td class="c41 c94" colspan="1" rowspan="1"><p class="c7 c37 c0"><span class="c11">Field</span></p></td><td class="c24" colspan="1" rowspan="1"><p class="c20 c0"><span class="c81 c11">Type</span></p></td><td class="c89 c41" colspan="1" rowspan="1"><p class="c20 c0"><span class="c11">Required </span></p></td><td class="c122 c41" colspan="1" rowspan="1"><p class="c7 c0 c70"><span class="c11">Description </span></p></td></tr><tr class="c5"><td class="c94" colspan="1" rowspan="1"><p class="c7 c14 c0"><span class="c4">rating</span></p></td><td class="c90" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c89" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c122" colspan="1" rowspan="1"><p class="c7 c0"><span class="c34">Must be a value from the </span><span class="c8"><a class="c23" href="/roku-feed-parental-ratings/">Direct Publisher Feed - Parental Ratings</a></span><span class="c4"> article.</span></p></td></tr><tr class="c5"><td class="c94 c31" colspan="1" rowspan="1"><a id="id.hjllj01l0oco"></a><p class="c7 c14 c0"><span class="c4">ratingSource</span></p></td><td class="c16" colspan="1" rowspan="1"><p class="c20 c0"><span class="c1">enum</span></p></td><td class="c89 c31" colspan="1" rowspan="1"><p class="c20 c0"><span class="c4">Required</span></p></td><td class="c122 c31" colspan="1" rowspan="1"><p class="c7 c0"><span class="c4">Must be one of the following:</span></p><p class="c7 c0 c17"><span class="c4"></span></p><ul class="c28 lst-kix_2pzc0ft104x2-0 start"><li class="c7 c49 c0"><span class="c4">BBFC</span></li><li class="c7 c49 c0"><span class="c4">CHVRS</span></li><li class="c7 c49 c0"><span class="c4">CPR</span></li><li class="c7 c49 c0"><span class="c4">MPAA</span></li><li class="c7 c49 c0"><span class="c4">UK_CP</span></li><li class="c7 c49 c0"><span class="c4">USA_PR</span></li></ul><p class="c7 c0 c17"><span class="c4"></span></p><p class="c7 c0"><span class="c34">Check the </span><span class="c8"><a class="c23" href="#h.cy3ovme5bxlp">Direct Publisher Feed - Parental Ratings</a></span><span class="c4"> article for more information.</span></p></td></tr></tbody></table>

Rating Object Example:

```json
{
  "rating": "PG",
  "ratingSource": "USA_PR"
}
```

***
## credit
Child object of property:

* `movie`
* `shortFormVideo`
* `series`
* `series` -> `episodes` -> `episode`
* `tvSpecial`

This object represents a single person in the credits of a video content.



**Credit Object Example:**

``` json
{
  "name": "Douglas N. Adams",
  "role": "screenwriter",
  "birthDate": "1952-03-11"
}
```

***

# Change Log

* **2016-08-18** - Removed UHD as an option from trickPlayFile -> quality.
* **2016-08-11** - Added SD to the qualities available for `video` -> `quality`. Updated `shortFormVideo`, `releaseDate` is now a required property.
* **2016-07-28** - Fixed `playlist` -> `itemIds` property description to not include episodes.
* **2016-07-18** - Updated `thumbnail` property description.
* **2016-07-08** - Updated `shortDescription` limit from 60 to 200 characters. Added `adBreaks` property to `content`.
* **2016-05-17** - Updated objects and properties descriptions, added horizontal lines between objects to improve reading, added a few more examples.
* **2016-04-25** - All properties documented with Name, Type, Required, and Description fields.
* **2016-04-14** - Document created.

# References

* JSON Schema Draft 4: http://json-schema.org/latest/json-schema-core.html
* ISO 8601: http://www.iso.org/iso/home/standards/iso8601.htm
* JSON Schema Validator: http://www.jsonschemavalidator.net/
* JSON Schema Lint: http://jsonschemalint.com/draft4/
