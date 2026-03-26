* Rendering Methods - 4 types hote hain:

  * CSR (Client Side Rendering)
  * SSR (Server Side Rendering)
  * SSG (Static Site Generation)
  * ISR (Incremental Static Regeneration)

* Inko samajhne ka best way = use case + data ka nature (kitna frequently change hota hai)

* CSR

  * Server ek basic HTML file bhejta hai, baaki sab rendering browser me JS se hoti hai

  * Initial load slow hota hai kyunki JS download + execute hota hai

  * SEO weak hota hai kyunki initial HTML me content nahi hota

  * Use case:

    * dashboards
    * internal tools
    * highly interactive apps

  * Key point:

    * ek baar load ho gaya to navigation fast hota hai (SPA behaviour)

* SSR

  * Har request par server HTML generate karke bhejta hai

  * Isliye user ko ready content milta hai (better SEO + fast first paint)

  * Har refresh par naya data milta hai

  * Use case:

    * e-commerce product pages
    * dynamic content jaha data frequently change hota hai

  * Tradeoff:

    * server load zyada hota hai
    * scaling costly ho sakta hai

* SSG

  * Pages build time par hi generate ho jaate hain

  * Baad me same static files serve hoti hain (CDN se bhi serve ho sakti hain)

  * Performance best hoti hai

  * Use case:

    * blogs
    * documentation
    * landing pages

  * Tradeoff:

    * data change hone par rebuild karna padta hai
    * real-time updates nahi milte

* ISR

  * SSG ka improved version hai

  * Pages initially static hote hain but ek time interval ke baad regenerate ho jaate hain

  * User ko fast response milta hai + data bhi eventually update hota hai

  * Use case:

    * news articles
    * product listings
    * content jo kabhi-kabhi update hota hai

  * Key point:

    * stale data thode time ke liye serve ho sakta hai (eventual consistency)

* Simple samajh:

  CSR → browser render karega
  SSR → server har request par render karega
  SSG → build time par ek baar render
  ISR → build + interval ke baad re-render

* In One line :
  Rendering ka matlab hai HTML kab (build time ya request time) aur kaha (client ya server) generate ho raha hai
