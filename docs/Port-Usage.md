# Port Usage


## Information

It's ideal for local development to run all API's and stream Services locally.

In the future it will be via docker, but for now the Port mappings.

As I can't be sure, that the 8080-8089 port range is unused by some users,
i'll be using the 8090-8099 port range.

## Mapping Table

 Port | Service
------|---------
 8090 | HTTP - OpenAPI Specifications
 8091 | HTTP - File Streaming
 8092 | S3 Instance
 8083 | Information V1 API
 8084 | mediaStream V1 API
 8085 | Information DB Driver V1 API

### About Service 8091

It is a simple http server service serving m3u8 library.

### It's structure

* /
  * /m3u8
    * /{some random id}
      * playlist.m3u8 and all qualities
  * /videos
    * mp4 files - not converted
  * /images
    * for posts in the future??? maybe???
  * /thumbnails
    * video thumbnails
