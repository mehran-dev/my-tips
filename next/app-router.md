client-server waterfall
import "server-only"

lazy loading 2 ways :

- A) dynamic (()=>import("name-package").then(mod=>mod.x)) // x= exported name component name
- B) react suspense

lazy loading => ssr

```javascript

// route segment config
export  dynamic="auto"
export  dynamicParams=true
export  revalidate=false
export  fetchCache="auto"
export  runtime="edge"|"node"
export  preferedRegion="auto"


```

middleware

- custom matcher
- conditional statement

. you can add cookie in middleware

{revalidatePath} from "next/catch"

headless vs serverless

shop/[[...slug]]/page => slug is optional

parallel routes
اجازه میده جدا استریم بشن
و جدا ارور و لودینگ داشته باشن
اجازه رندر شسدن شرطی هم بهت میده

layout @team - @members

لیوت بالا پراپ جدا میگیره

layout (props :{
children , team , members

})

app/page.js === app/@children/pagr.js

---

import {cookies} from "next/headers"
x= cookies()
token= x.get(token) // it is readonly

prima / stripe

get url //

usePathName , useSelectedLayoutSegment(s)

app router built on react-server-components

<Link> refecthes automatic 
router.prefetch()

dynamic segment = dynamic route

generate meta data - genericStaticParams

fetch(url , {cache="no-store"}) === getServerSideProps

```
export dynamic = "dynamic-force" (ssr)
export dynamic = "dynamic-static" (ssg)
export dynamicParams = true
export revalidate = 0

```

import {experimental_useOptimisticUpdate} from "react"

```javascript
ssr -runtime {getInitialProps - getServerSideProps}
static - no initial props
ssg - static html
isr - uses revalidate getStaticProps


```

fallback-true vs block

getStaticPath is required for ssg

### parallel route

@users
@articles

they can have their own loading and articles

s3 liara is better than cloudinary

reacttraining.com
