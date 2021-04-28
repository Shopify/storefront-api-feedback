# Storefront API Evolution Changes

### Top Level
* Added `@oneOf` Directive
  * Denotes that one, and only one of an `input` object's arguments must be specified. 
  * https://github.com/graphql/graphql-spec/pull/825
* Added `OnlineStorePublishable` Interface
  * Conforming objects expose an optional `onlineStoreUrl` field which represents their presence on the Online Store channel.
* Renamed `Mutation` to `MutationRoot`

### Type Changes

#### Article
* Added `OnlineStorePublishable`
* Renamed `authorV2` to `author`
* Changed `content: String!` to `content: RichText!`
* Removed `contentHtml: HTML!`
* Changed `excerpt: String!` to `excerpt: RichText!`
* Removed `excerptHtml: HTML!`
* Removed `url`

#### Blog
* Added `OnlineStorePublishable`
* Removed `url`

#### Collection
* Added `OnlineStorePublishable`
* Changed `description: String!` to `description: RichText!`
* Removed `descriptionHtml: HTML!`

#### Comment
* Changed `content: String!` to `content: RichText!`
* Removed `contentHtml: HTML!`

#### Domain
* Removed

#### Image
* Renamed `originalSrc` to `url`
* Renamed `transformedSrc` to `transformedUrl`

#### Money
* Renamed `MoneyV2` to `Money`

#### Page
* Added `OnlineStorePublishable`
* Renamed `body: Html!` to `content: RichText!`
* Removed `bodySummary`

#### Product
* Added `OnlineStorePublishable`
* Changed `description: String!` to `description: RichText!`
* Removed `descriptionHtml: HTML!`
* Removed `presentmentPriceRanges`
* Added `recommendations: [Product]!`
* Renamed `variantMatchingOptions(selectedOptions:)` to `variant(matching:)`

#### ProductVariant
* Removed `available`
* Renamed `compare_at_price_v2` to `compare_at_price`
* Removed `presentmentPrices`
* Renamed `price_v2` to `price`
* Removed `presentmentUnitPrices`

#### QueryRoot
* Renamed `blogByHandle` to `blog(by: BlogLookupInput(id: ID, handle: String)!)`
* Renamed `collectionByHandle` to `collection(by: CollectionLookupInput(id: ID, handle: String)!)`
* Renamed `pageByHandle` to `page(by: PageLookupInput(id: ID, handle: String)!)`
* Renamed `productByHandle` to `product(by: ProductLookupInput(id: ID, handle: String)!)`
* Removed `productRecommendations`

#### RichText
* Added `RichText`
  * Added `html: Html!`
  * Added `text(truncateAt: Int): String!`

#### Shop
* Renamed `primaryDomain: Domain` to `url: Url`
* Removed deprecated fields

#### ShopPolicy
* Renamed `body: String` to `content: RichText`
