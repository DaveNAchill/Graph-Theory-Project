# Irish Constituencies Neo4j Database
###### David Needham, G00263842

## Introduction
This is a Neo4j Graph of the General Election 2016 in Ireland.
This graph shows the differnt relationships between the candidates.

## Database
Used the following lines of code to create the nodes for Candidate, Party and Constituency.

`CREATE(n:Candidate{name:'Gerry Adams',gender:'Male',constituency:'Louth',party:'Sinn Fein'});`

`CREATE(p:Party{name:'Sinn Fein'});`

`CREATE(c:Constituency{name:'Louth'});`

For the Relationships I used the following:
I was unable to get them to work, but here is what I tried:

```
match (constituency:Constituency {constituency:"Louth"}) 
with constituency
match (candidate:Candidate {constituency:"Louth"})
create (candidate)-[r:FROM]->(constituency) 
return constituency,candidate;
```
## Queries
Summarise your three queries here.
Then explain them one by one in the following sections.

#### Query one title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query two title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

#### Query three title
This query retreives the Bacon number of an actor...
```cypher
MATCH
	(Bacon)
RETURN
	Bacon;
```

## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. [Storyful on Github](https://github.com/storyful/irish-elections), Source of .csv file for candidates.
3. [Stack Overflow](http://stackoverflow.com/questions/36519209/neo4j-graph-database-relationships/36519912#36519912), For help with Realationships between nodes.
