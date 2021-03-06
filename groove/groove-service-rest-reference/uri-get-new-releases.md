---
title: Discover the new releases API for Groove Music| Groove Services
description:  Get a list of new releases in Groove Music catalog with this API
keywords: groove music, groove api, groove new releases
author: sakley
ms.assetid: a6104680-abbb-416d-a907-158adbae505b
---

# GET (/1/content/{namespace}/newreleases)
Discover new releases.

-   [Remarks](#remarks)
-   [URI parameters](#uri-parameters)
-   [Response object](#response-object)
-   [Examples](#examples)

## Remarks
The new releases request is composed of mandatory and optional URL parts and query parameters. A request containing all parameters would look like the following string:
```
GET /1/content/{namespace}/newreleases?genre={genre}&language={language}&country={country}

Authorization: Bearer [...]
```
For parameters common to every Groove RESTful API, see [Parameters common to every Groove RESTful API](common-parameters.md). For a table of error codes, see [Error (JSON)](JSON-Error.md). For HTTP status codes, see [Groove RESTful API HTTP Status Codes](http-status-codes.md).

## URI parameters
| **Parameter** | **Type** | **Description**                                                                                                                                                                                                                                                                                                                                    |
|---------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| genre         | string   | Optional (used only when requesting new releases). Specifies the genre for which you want to see new releases. If it is not used, the API will return new releases in all available genres. Possible values may be obtained using the [browse genres API](uri-get-genres.md) and must be URL-encoded. |

## Response object
[ContentResponse (JSON)](JSON-ContentResponse.md)

## Examples
### New releases (all genres)
#### Request
```http
GET /1/content/music/newreleases

Authorization: Bearer [...]
```

#### Response
```json
{
  "Results": {
    "Items": [
      {
        "Type": "Albums",
        "Album": {
          "ReleaseDate": "2013-11-04T00:00:00Z",
          "Duration": "00:04:00",
          "TrackCount": 1,
          "IsExplicit": false,
          "LabelName": "RCA Records Label",
          "Genres": [
            "Pop"
          ],
          "Subgenres": [
            "Contemporary Pop"
          ],
          "AlbumType": "Single",
          "Artists": [
            {
              "Role": "Main",
              "Artist": {
                "Id": "music.BF100000-0200-11DB-89CA-0019B92A3933",
                "Name": "Britney Spears",
                "ImageUrl": "https://musicimage.xboxlive.com/content/music.BF100000-0200-11DB-89CA-0019B92A3933/image?locale=en-US",
                "Link": "https://music.microsoft.com/Artist/BF100000-0200-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
                "Source": "Catalog"
              }
            }
          ],
          "Id": "music.6B37F707-0100-11DB-89CA-0019B92A3933",
          "Name": "Perfume",
          "ImageUrl": "https://musicimage.xboxlive.com/content/music.6B37F707-0100-11DB-89CA-0019B92A3933/image?locale=en-US",
          "Link": "https://music.microsoft.com/Album/6B37F707-0100-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
          "OtherIds": {
            "music.amg": "R  2863588"
          },
          "Source": "Catalog"
        }
      },
      {
        "Type": "Albums",
        "Album": {
          "ReleaseDate": "2013-11-01T00:00:00Z",
          "Duration": "00:03:40",
          "TrackCount": 1,
          "IsExplicit": true,
          "LabelName": "Rebel Rock/Grand Hustle/Atlantic",
          "Genres": [
            "Hip Hop"
          ],
          "Subgenres": [
            "Contemporary Hip Hop"
          ],
          "AlbumType": "Single",
          "Artists": [
            {
              "Role": "Main",
              "Artist": {
                "Id": "music.8E2C0300-0200-11DB-89CA-0019B92A3933",
                "Name": "B.o.B",
                "ImageUrl": "https://musicimage.xboxlive.com/content/music.8E2C0300-0200-11DB-89CA-0019B92A3933/image?locale=en-US",
                "Link": "https://music.microsoft.com/Artist/8E2C0300-0200-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
                "Source": "Catalog"
              }
            }
          ],
          "Id": "music.A2C7F607-0100-11DB-89CA-0019B92A3933",
          "Name": "All I Want",
          "ImageUrl": "https://musicimage.xboxlive.com/content/music.A2C7F607-0100-11DB-89CA-0019B92A3933/image?locale=en-US",
          "Link": "https://music.microsoft.com/Album/A2C7F607-0100-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
          "Source": "Catalog"
        }
      },
      {
        [...]
      }
    ],
    "TotalItemCount": 30
  }
}
```

### New releases (specific FR genre)
#### Request
```http
GET /1/content/music/newreleases?country=FR&genre=Rock

Authorization: Bearer [...]
```

#### Response
```json
{
  "Results": {
    "Items": [
      {
        "Type": "Albums",
        "Album": {
          "ReleaseDate": "2014-06-04T00:00:00Z",
          "Duration": "01:07:28",
          "TrackCount": 13,
          "IsExplicit": false,
          "LabelName": "Nuclear Blast",
          "Genres": [
            "Rock"
          ],
          "Subgenres": [
            "Hard Rock / Metal"
          ],
          "AlbumType": "Album",
          "Artists": [
            {
              "Role": "Main",
              "Artist": {
                "Id": "music.A3730400-0200-11DB-89CA-0019B92A3933",
                "Name": "Equilibrium",
                "ImageUrl": "https://musicimage.xboxlive.com/content/music.A3730400-0200-11DB-89CA-0019B92A3933/image?locale=fr-FR",
                "Link": "https://music.microsoft.com/Artist/A3730400-0200-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
                "Source": "Catalog"
              }
            }
          ],
          "Id": "music.8CB95D08-0100-11DB-89CA-0019B92A3933",
          "Name": "Erdentempel",
          "ImageUrl": "https://musicimage.xboxlive.com/content/music.8CB95D08-0100-11DB-89CA-0019B92A3933/image?locale=fr-FR",
          "Link": "https://music.microsoft.com/Album/8CB95D08-0100-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
          "Source": "Catalog"
        }
      },
      {
        "Type": "Albums",
        "Album": {
          "ReleaseDate": "2014-06-05T00:00:00Z",
          "Duration": "00:40:49",
          "TrackCount": 9,
          "IsExplicit": false,
          "LabelName": "Kamakans Records",
          "Genres": [
            "Rock"
          ],
          "Subgenres": [
            "Hard Rock / Metal"
          ],
          "AlbumType": "Album",
          "Artists": [
            {
              "Role": "Main",
              "Artist": {
                "Id": "music.BD1B5A00-0200-11DB-89CA-0019B92A3933",
                "Name": "Voodoopriest",
                "ImageUrl": "https://musicimage.xboxlive.com/content/music.BD1B5A00-0200-11DB-89CA-0019B92A3933/image?locale=fr-FR",
                "Link": "https://music.microsoft.com/Artist/BD1B5A00-0200-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
                "Source": "Catalog"
              }
            }
          ],
          "Id": "music.8F855E08-0100-11DB-89CA-0019B92A3933",
          "Name": "Mandu",
          "ImageUrl": "https://musicimage.xboxlive.com/content/music.8F855E08-0100-11DB-89CA-0019B92A3933/image?locale=fr-FR",
          "Link": "https://music.microsoft.com/Album/8F855E08-0100-11DB-89CA-0019B92A3933?partnerID=AwesomePartner",
          "Source": "Catalog"
        }
      },
      {
        [...]
      }
    ],
    "TotalItemCount": 30
  }
}
```

#### Parent
[Groove Service REST Reference](overview.md)
