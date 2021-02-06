# magento2-graphql-types

This repository exports TypeScript types for the current Magento 2 version GraphQL API.

You can treat the types as helpers for when you work with M2 GraphQL.

## Versioning

Since this repo and project is dedicated to Magento 2, the _first_ two digits in this package's semver will always match the _last_ two digits of the current Magento version. For example, for Magento 2.4.1, this package will have version number 4.1.x. The last number will start at 0, then be used for patches or bugfixes.

Another example: For Magento 2.6.5, this package will use the version numbers 6.5.0, 6.5.1, 6.5.2, etc.

## A Contrived Example

```js
import fetch from 'node-fetch'
import { CmsPage } from 'magento2-graphql-types'

const getData = async () => {
    const res = await fetch('https://venia.magento.com/graphql?query=query+getCmsPage%28%24id%3AInt%21%29%7BcmsPage%28id%3A%24id%29%7Burl_key+content+content_heading+title+page_layout+meta_title+meta_keywords+meta_description+__typename%7D%7D&operationName=getCmsPage&variables=%7B%22id%22%3A7%7D')
    const resJson = await res.json()
    const data = resJson.data.cmsPage as CmsPage
    console.log(data.title)
}

getData()
```

## Contributing

Please note that all contributions fall under the MIT license which this project uses.

This project is not officially affiliated with Adobe or Magento.