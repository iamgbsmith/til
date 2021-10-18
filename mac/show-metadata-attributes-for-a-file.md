# Show Metadata Attributes For A File

__Category: Mac__

You can show metadata attributes for a file using `mdls` from the command line.

For example, when running the mdls command against a PDF file:

```shell
mdls 32890-Civic-TypeR-Brochure.pdf
```

Output:

```shell
mdls 32890-Civic-TypeR-Brochure.pdf 
_kMDItemDisplayNameWithExtensions      = "32890-Civic-TypeR-Brochure.pdf"
kMDItemContentCreationDate             = 2019-05-06 09:25:37 +0000
kMDItemContentCreationDate_Ranking     = 2019-05-06 00:00:00 +0000
kMDItemContentModificationDate         = 2019-05-06 09:25:38 +0000
kMDItemContentModificationDate_Ranking = 2019-05-06 00:00:00 +0000
kMDItemContentType                     = "com.adobe.pdf"
kMDItemContentTypeTree                 = (
    "com.adobe.pdf",
    "public.data",
    "public.item",
    "public.composite-content",
    "public.content"
)
kMDItemCreator                         = "Adobe InDesign CS6 (Macintosh)"
kMDItemDateAdded                       = 2019-05-06 09:25:37 +0000
kMDItemDateAdded_Ranking               = 2019-05-06 00:00:00 +0000
kMDItemDisplayName                     = "32890-Civic-TypeR-Brochure.pdf"
kMDItemDocumentIdentifier              = 0
kMDItemEncodingApplications            = (
    "Adobe PDF Library 10.0.1"
)
kMDItemFSContentChangeDate             = 2019-05-06 09:25:38 +0000
kMDItemFSCreationDate                  = 2019-05-06 09:25:37 +0000
kMDItemFSCreatorCode                   = ""
kMDItemFSFinderFlags                   = 0
kMDItemFSHasCustomIcon                 = (null)
kMDItemFSInvisible                     = 0
kMDItemFSIsExtensionHidden             = 0
kMDItemFSIsStationery                  = (null)
kMDItemFSLabel                         = 0
kMDItemFSName                          = "32890-Civic-TypeR-Brochure.pdf"
kMDItemFSNodeCount                     = (null)
kMDItemFSOwnerGroupID                  = 20
kMDItemFSOwnerUserID                   = 501
kMDItemFSSize                          = 2181561
kMDItemFSTypeCode                      = ""
kMDItemInterestingDate_Ranking         = 2019-05-06 00:00:00 +0000
kMDItemKind                            = "PDF document"
kMDItemLogicalSize                     = 2181561
kMDItemNumberOfPages                   = 9
kMDItemPageHeight                      = 737.008
kMDItemPageWidth                       = 595.276
kMDItemPhysicalSize                    = 2183168
kMDItemSecurityMethod                  = "None"
kMDItemVersion                         = "1.7"
kMDItemWhereFroms                      = (
    "https://www.honda.co.nz/assets/sm/upload/bj/py/er/l8/32890%20Civic%20Type%20R%20Brochure.pdf?k=85edeb67fb"
)
```

Detail for photos will include latitude, longitude, and the type of camera device used.
