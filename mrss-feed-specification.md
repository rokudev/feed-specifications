# MRSS Feed Specification

MRSS Feeds for Direct Publisher follows the [MRSS 1.5.1 specification](http://www.rssboard.org/media-rss), and [RSS 2.0 specification](http://www.rssboard.org/rss-specification), with a few modifications on which elements are required or optional. These changes focus on ensuring customers have all the information necessary for the best experience with your channel and the Roku platform.

This document has detailed information on the MRSS elements you can use to build out a Direct Publisher-compatible MRSS feed, as well as examples to help along the way. We only parse the elements described in this document, and any other provided will be ignored.

In the example Roku Channel image below, you can see where the fields of your MRSS feed will be used:

![Roku Channel Example](https://roku-developer-home-ghost-staging.s3.amazonaws.com/2016/Jul/cm9rdV9wcmV2aWV3LTE0Njc4NTg5MzU3OTk=.png)
##### Roku Channel Example

- - -

## Elements List
Elements marked with * are required.

* Channel
  * lastBuildDate
* Item
  * guid\*
  * pubDate\*
  * media:title\*
  * media:description\*
  * media:category\*
  * media:keywords\*
  * media:thumbnail\*
  * media:content\*
  * media:subTitle
  * dcterms:valid

## Elements Details
Following is a complete list of the elements that Direct Publisher supports, including a description and example of each one.
### Channel Sub-Elements
The following should be sub-elements of a `<channel>` tag.

***
#### lastBuildDate
*Optional*

The last time the feed was updated.

```xml
<lastBuildDate>Sat, 07 Sep 2016 09:42:31 GMT<lastBuildDate>
```
***

### Item Sub-Elements
The following should be sub-elements of an `<item>` tag.

***
#### guid
*Required*

The unique and immutable id for the video.

```xml
<guid>https://example.org/cdn/video/vaaaXaaX</guid>
```

***
#### pubDate
*Required*

The date the video first became available.

```xml
<pubDate>Sat, 07 Sep 2016 09:42:31 GMT</pubDate>
```

***
#### media:title
*Required*

The video title. We use this value for matching. Please use plain text and don’t include extra information like year, version label, etc. You can also use `<title>` in its place.

```xml
<media:title>The Best Show Ever</media:title>
```

***
#### media:description
*Required*

A description of the video that **does not exceed 200 characters**. The text will be clipped if longer. You can also use `<description>` in its place.

```xml
<media:description>So long, and thanks for all the fish.</media:description>
```

***
#### media:category
*Required\* - Either `media:category` or `media:keywords` are required.*

One or more categories. Categories are used as tags in Direct Publisher, which can help you organize your content so your users can quickly find what they want. The names you use here won't be directly displayed to your viewers. You can find more information about categories and tags in the [Partner Integration Guide](/home/docs/develop/direct-publisher/partner-integration-guide/).

```xml
<media:category>Cooking Shows</media:category>
```

or:

```xml
<media:category>cooking</media:category>
<media:category>reality</media:category>
```

***
#### media:keywords
*Required\* - Either `media:category` or `media:keywords` are required.*

A comma-separated list of keywords. Similar to categories, keywords are used as tags in the Channel Builder, which can help you organize your content so your users can quickly find what they want. The names you use here won't be directly displayed to your viewers. You can find more information about categories and tags in the [Partner Integration Guide](/home/docs/develop/direct-publisher/partner-integration-guide/).

```xml
<media:keywords>humans, space, travel, exploration</media:keywords>
```

***
#### media:thumbnail
*Required*

The thumbnail is used within your application and in the search results. The image size must be 800x450 (width x height) or larger, with a 16x9 aspect ratio. Supported formats are JPG or TIFF.

```xml
<media:thumbnail url="http://example.org/cdn/thumbs/42/lkmfaAAmA.jpg" />
```

#### Flags

**url** - *Required* - The URL of the thumbnail.

***
#### media:content
*Required*

The actual video file(s). For more information on supported formats, see [Audio and Video Support](https://github.com/rokudev/docs/blob/master/develop/specifications/audio-video-support.md).

```xml
<media:content
   url="https://example.org/videos/your-video-id.mp4"
   duration="74.74" />
```

##### Flags
**url** - *Required* - The URL of the video file.

**duration** - *Required* - The duration of the video in seconds.

**bitrate** - *Optional* - The bitrate of the file. Must be provided if multiple single bitrate (e.g., MP4) files are provided.

**lang** - *Optional* - The original language of the video.

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

One or more subtitle files for the video. For more information on supported subtitle formats please check the [Closed Caption / Subtitle Support](https://developer-docs-staging.eng.roku.com/closed-caption-subtitles-support/) article.

```xml
<media:subTitle
   lang="en-us"
   href="http://www.example.org/cdn/subtitles/subtitle.srt" />
```

##### Flags
**href** - *Required* - The URL of the subtitle file.

**lang** - *Required* - The language of the subtitle file.

***
#### dcterms:valid
*Optional*

The validity period for the video. The video will not be displayed to the user unless it is within the validity period.

```xml
<dcterms:valid>
   start=2016-07-13T09:42:31+00:00;
   end=2016-07-13T09:42:31+00:00;
   scheme=W3C-DTF
</dcterms:valid>
```

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
