# Researchspace front page
http://localhost:10214/resource/:ProjectDashboard  
http://localhost:10214/resource/Start  
```[[> rsp:ProjectDashboard]]  ```  


＃　trig file format 
```<http://localhost/hm/graph> {
<uri> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <uri> . 
}
```

# run a search 

```
SELECT * WHERE {
  <uri> ?pred ?obj .
} 
LIMIT 50
```

# Grade of Relics

Cultural relic collections are divided into precious cultural relics and ordinary cultural relics. Precious cultural relics are divided into the first class, the second class and the third class. Typical cultural relics that have especially important historical, artistic and scientific values are first-class cultural relics; those that have important historical, artistic and scientific values are second-class cultural relics; and those that have relatively important historical, artistic and scientific values are third-class cultural relics. Cultural relics that have certain historical, artistic and scientific values are ordinary cultural relics.


# change of IIIF server
https://github.com/researchspace/researchspace/commit/e14d0ebb1c58fe93e722a9ff983614da47f4f8cf

old  server : iiif-server-url='/proxy/IIIF'
new server:  iiif-server-url='/proxy/iiif-server/iiif/1' '/proxy/iiif-server/iiif/2'

- itemcard media
- ResourceContent.html


# change of search and KG. 
KnowledgeMapOntodiaConfig
http://localhost:10214/resource/rsp:SearchContent

# search on osm


PREFIX osm: <http://www.researchspace.org/resource/system/services/osm/>
```
SELECT * WHERE {
  ?subject osm:q "Venice" ;
    osm:display_name ?display_name ;
    osm:geotext ?geo_text ;
    osm:wikidata ?wikidata ;
    osm:importance ?score .
}
        
```



# delete graph 

```
DELETE { 
  ?s ?p ?o.
} WHERE {
  GRPAH <RelationshipGraph> {
    ?s ?p ?p.
  }
}
```
# update data
```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#> 

INSERT DATA
{ 
  <uri> rdfs:label "word"@zh .
                         
}

```
# url of sepcial resource

```
/resource/feiquan3d
/assets/Duyou3d.mp4
```
# 
# sparql bind and concat

BIND(CONCAT("STRING_1",?thing_1,"STRING_2") AS ?what 
