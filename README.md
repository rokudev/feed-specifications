# Direct Publisher Feed Specifications

### Overview
Your content is the most important part of your application. With Direct Publisher, you can now create a channel using an existing MRSS feed or the Direct Publisher feed (JSON). The following specifications outline the necessary information required for feed-based channels.

- - -

## Feed Formats

### [Direct Publisher Feed Format (JSON)](https://github.com/rokudev/feed-specifications/blob/master/direct-publisher-feed-specification.md)
This is a **JSON format** that is supported for all types of content, including Movies, Series and TV Specials that require **detailed metadata**. The Direct Publisher Feed format also supports all Direct Publisher functionality, including the ability to specify the UI categories and category mapping within the feed itself. You can find more detailed information in our [Direct Publisher Feed Specification Guide](https://github.com/rokudev/feed-specifications/blob/master/direct-publisher-feed-specification.md).

### [MRSS Feeds](https://github.com/rokudev/feed-specifications/blob/master/mrss-feed-specification.md)
This format is supported for short-form content (videos that are generally less than 20 minutes long, and are not TV Shows or Movies). This allows partners that have existing MRSS feeds to re-purpose them with little or no changes for Direct Publisher. You can find more detailed information in our [MRSS Specification Guide](https://github.com/rokudev/feed-specifications/blob/master/mrss-feed-specification.md).

## Content Types
A feed can contain one or more of the following types of content:

* Movies
* Series
* TV Specials
* Short-form videos (they are generally less than 20 minutes long, and are not TV Shows or Movies)

**Note:** The metadata required will vary based on the type of content, as described in the MRSS Specification Guide, and the Direct Publisher Feed Specification Guide.
