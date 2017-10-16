# MRSS Feed Specification

### Overview

Direct Publisher supports catalog feeds of content for launching channels on the Roku Publishing Platform. Specifically, we support MRSS feeds with required fields to ensure have the best experience with a channel.

This specification has detailed information on the MRSS elements you can use to build out a Direct Publisher-compatible MRSS feed, as well as examples to help along the way.

> :information_source: **Note:** only parse the elements described in this spec. Any other elements provided will be ignored.

- - -

#### Feed Formats
MRSS Feeds for Direct Publisher are based on the following specifications:
* [MRSS 1.5.1 specification](http://www.rssboard.org/media-rss)
* [RSS 2.0 specification](http://www.rssboard.org/rss-specification)

In addition, we indicate which items which elements are required and/or optional.

In the example Roku Channel image below, you can see where the fields of your MRSS feed will be used:

![Roku Channel Example](https://s3.amazonaws.com/roku-blog/developer/files/2017/07/mrss-content.jpg)
<p align=center><i>Roku Channel Example</i></p>

The following is a complete list of the elements that Direct Publisher supports along with descriptions and examples.

**Elements List:**

> :information_source: Elements marked with * are required.

* Channel
  * [lastBuildDate](#lastbuilddate)
* [Item](#item)
  * [guid\*](#guid)
  * [pubDate\*](#pubdate)
  * [media:title\*](#mediatitle)
  * [media:description\*](#mediadescription)
  * [media:category\*](#mediacategory)
  * [media:keywords\*](#mediakeywords)
  * [media:thumbnail\*](#mediathumbnail)
  * [media:content\*](#mediacontent)
  * [media:subTitle](#mediasubtitle)
  * [dcterms:valid](#dctermsvalid)

---

## Channel Sub-Elements
The following are sub-elements of a `<channel>` tag:

### lastBuildDate
*Optional*

The last time the feed was updated, in the [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00

**Example:**
```xml
<lastBuildDate>2016-09-07T09:42:31+00:00<lastBuildDate>
```
---

## Item

Each `<item>` in an MRSS feed correlates to one video / content item.

**Example:**
```xml
<item>
  <guid>https://example.org/cdn/video/vaaaXaaX</guid>
  <pubDate>2016-09-07T09:42:31+00:00</pubDate>
  <media:title>The Best Show Ever</media:title>
  <media:description>So long, and thanks for all the fish.</media:description>
  <media:category>cooking</media:category>
  <media:category>reality</media:category>
  <media:thumbnail url="http://example.org/cdn/thumbs/42/lkmfaAAmA.jpg" />
  <media:content
   url="https://example.org/videos/your-video-id.mp4"
   duration="74.74"
   bitrate="2500"
   language="en-us" />
  <media:subTitle
    lang="en-us"
    href="http://www.example.org/cdn/subtitles/subtitle.srt" />
</item>
```

The following are sub-elements of an `<item>` tag:

### guid
*Required*

The unique and immutable id for the video.

**Example:**
```xml
<guid>https://example.org/cdn/video/vaaaXaaX</guid>
```

***
### pubDate
*Required*

The date the video first became available, in the [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00

**Example:**
```xml
<pubDate>2016-09-07T09:42:31+00:00</pubDate>
```

***
### media:title
*Required*

The video title. We use this value for matching. Please use plain text and don’t include extra information like year, version label, etc. You can also use `<title>` in its place.

**Example:**
```xml
<media:title>The Best Show Ever</media:title>
```

***
### media:description
*Required*

A description of the video that **does not exceed 200 characters**. The text will be clipped if longer. You can also use `<description>` in its place.

**Example:**
```xml
<media:description>So long, and thanks for all the fish.</media:description>
```

***
### media:category
*Required - Either `media:category` or `media:keywords` are required.*

One or more categories. Categories are used as tags in Direct Publisher, which can help you organize your content so your users can quickly find what they want. The names you use here won't be directly displayed to your viewers. You can find more information about categories and tags in [Content Specifications](https://developer.roku.com/publish/content-specifications/content-spec-index#categories).

**Examples:**
```xml
<media:category>Cooking Shows</media:category>
```

or:

```xml
<media:category>cooking</media:category>
<media:category>reality</media:category>
```

***
### media:keywords
*Required - Either `media:category` or `media:keywords` are required.*

A comma-separated list of keywords. Similar to categories, keywords are used as tags in Direct Publisher, which can help you organize your content so your users can quickly find what they want. The names you use here won't be directly displayed to your viewers. You can find more information about categories and tags in [Content Specifications](https://developer.roku.com/publish/content-specifications/content-spec-index#categories).

**Example:**
```xml
<media:keywords>humans, space, travel, exploration</media:keywords>
```

***
### media:thumbnail
*Required*

The thumbnail is used within your application and in the search results. The image size must be 800x450 (width x height) or larger, with a 16x9 aspect ratio. Supported formats are `JPG` or `TIFF`.

**Flag(s):**

| Flag | Required | Description |
| ---- | -------- | ----------- |
| url | Required | The URL of the thumbnail

**Example:**
```xml
<media:thumbnail url="http://example.org/cdn/thumbs/42/lkmfaAAmA.jpg" />
```

***
#### media:content
*Required*

The actual video file(s). For more information on supported formats, see [Audio and Video Support](https://sdkdocs.roku.com/display/sdkdoc/Audio+and+Video+Support).

**Flags:**

| Flag | Required | Description |
| ---- | -------- | ----------- |
| url | Required | The URL of the video file
| duration | Required | The duration of the video (in seconds)
| bitrate | Optional | The bitrate of the file. Must be provided if multiple single bitrate (e.g., MP4) files are provided.
| lang | Optional | The original language of the video

**Examples:**
```xml
<media:content
   url="https://example.org/videos/your-video-id.mp4"
   duration="74.74" />
```

```xml
<media:content
   url="https://example.org/videos/your-video-id.mp4"
   duration="74.74"
   bitrate="2500"
   language="en-us" />
```

***
#### media:subTitle
*Optional*

One or more subtitle files for the video. For more information on supported subtitle formats, see [Closed Caption / Subtitle Support](https://sdkdocs.roku.com/display/sdkdoc/Closed+Caption+Support).

**Flags:**

| Flag | Required | Description |
| ---- | -------- | ----------- |
| href | Required | The URL of the subtitle file
| lang | Required | The language of the subtitle file

**Example:**
```xml
<media:subTitle
   lang="en-us"
   href="http://www.example.org/cdn/subtitles/subtitle.srt" />
```

***
#### dcterms:valid
*Optional*

The validity period for the video. The video will not be displayed to the user unless it is within the validity period.

This field conforms to the [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format: {YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}+{TZ}. E.g.: 2015-11-11T22:21:37+00:00

**Example:**
```xml
<dcterms:valid>
   start=2016-07-13T09:42:31+00:00;
   end=2016-07-13T09:42:31+00:00;
   scheme=W3C-DTF
</dcterms:valid>
```

---

## Change Log

* **2016-07-08** - Updated `media:description` limit from 60 to 200 characters.
* **2016-07-06** - Removed Appendix, added links to external articles.
* **2016-05-17** - Updated elements description, added horizontal lines between elements to improve reading, updated examples, removed Elements Table.
* **2016-04-06** - Document created.

## References

* RSS 2.0 Specification: http://www.rssboard.org/rss-specification
* RSS 2.0 Specification (Harvard Law): http://cyber.law.harvard.edu/rss/rss.html
* MRSS 1.5.1 Specification: http://www.rssboard.org/media-rss
* RSS Best Practices: http://www.rssboard.org/rss-profile
