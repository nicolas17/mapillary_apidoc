# Images and Sequences

## Images

> Access an Mapillary image by key

```curl
https://d1cuyjsrcm0gby.cloudfront.net/<KEY>/thumb-320.jpg
```

> Make sure to replace `<KEY>` with the key of the image.



Mapillary images are photos contributed by users and made available on the website and through this API. The publicly accessible photos are stripped of information that may be sensitive for privacy reasons and are processed by face blurring and license plate blurring before they are made available. 



### Image key

Each Mapillary image has a unique identifier key. This key is part of the URL of image views when browsing the website, for example:
http://www.mapillary.com/map/im/<KEY>

The KEY is also used to retrieve information from the API. 

### Image license

Mapillary images are available under the [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/) (CC BY-SA 4.0).

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>

This license applies to all four versions of the photos, named "thumb-320.jpg", "thumb-640.jpg", "thumb-1024.jpg", and "thumb-2048.jpg" respectively.

Attribution should include a clearly visible link to mapillary.com or to the Mapillary photo page directly.

The images are also available under other licenses for commerical use if CC BY-SA is not appropriate for the commercial usage. 

Mapillary images are available using the following URL pattern:

`https://d1cuyjsrcm0gby.cloudfront.net/<KEY>/thumb-320.jpg`
`https://d1cuyjsrcm0gby.cloudfront.net/<KEY>/thumb-640.jpg`
`https://d1cuyjsrcm0gby.cloudfront.net/<KEY>/thumb-1024.jpg`
`https://d1cuyjsrcm0gby.cloudfront.net/<KEY>/thumb-2048.jpg`

<aside class="notice">
Make sure to replace `<KEY>` with the key of the image.
</aside>

## Sequences

All images are part of a sequence. Sequences are a continuous meaningful grouping of photos as the user pans or moves around. For example, driving a stretch of road. Mapillary encourages capture of images in sequences to maximize the connectedness of images and make sure it is possible to navigate to and from an image.

### Sequence key

Each Mapillary sequence has a unique identifier key. This key is visible under the info card when browsing an image view on the website and is used to retrieve information from the API. 

