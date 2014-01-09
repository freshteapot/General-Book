#Exploring cypher

##Cheatsheet
http://www.neo4j.org/assets/download/Neo4j_CheatSheet_v3.pdf


#Adding a document/node/entry

```
CREATE person={id: 123, name:"Chris", type: "user"}
```
We declare it to person. This way if we wanted, we could return it.

```
CREATE person={id: 123, name:"Chris", type: "user"}
RETURN person;
```

#Querying the index
For this query below to work you need to have set in the properties of your server.

```
node_auto_indexing = true
```

By default it is false. Which means you have to create your indexes when you add your node, or have reference to the node id.


```
START me=node:node_auto_index(name = "Chris"), fav=node:node_auto_index(name="Cats")
CREATE me-[:favorite]-fav
```

Find the node with the name "Chris" and find the node with the name Cats. Create a relationship with the name "favorite" that connects "Chris" to "Cats".

##Create a unique relationship with properties

```
START me=node:node_auto_index(name = "Chris")
CREATE UNIQUE me-[:favorite]-(newFav {name:"Car"})
```

##Using lucene style queries against the indexes.

```
START me=node:node_auto_index(name = "Chris" AND type = "user")
RETURN me.name;
```


##Traverse the nodes and find all those that do not have a type

```
START n=node(*)
WHERE NOT has(n.type)
RETURN n;
```


##Traverse the nodes and find all those that do have a type

```
START n=node(*)
WHERE has(n.type)
RETURN n;
```

##Traverse the nodes and find all those that do have a type and is not = user

```
START n=node(*)
WHERE has(n.type)
AND NOT(n.type="user")
RETURN n;
```

##Traverse the nodes and find all those that do have a type that is equal to user

```
START n=node(*)
WHERE n.type! = "user"
RETURN n;
```

##Traverse the nodes and find all those without a type and delete them and their relationships

```
START n=node(*)
MATCH n-[r]-()
WHERE NOT(has(n.type))
DELETE r,n;
```
