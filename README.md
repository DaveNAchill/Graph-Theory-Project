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

#### Shortest Path
This shortest between two candidates

```
MATCH (n:Candidate { name:"Gerry Adams" }),(n:Candidate { name:"Enda Kenny" }),
  p = shortestPath((n)-[*..15]-(n))
RETURN p
```

#### Match Candidates in the same Party

```
MATCH (n:Candidate), (p:Party)
WHERE n.party = "Fine Geal" AND p.name = "Fine Geal"
RETURN n,p;
```
#### Match Candidates in the same Constituency

```
MATCH (n:Candidate), (c:Constituency)
WHERE n.constituency = "Mayo" AND c.constituency = "Mayo"
RETURN n,c;
```


## References
1. [Neo4J website](http://neo4j.com/), the website of the Neo4j database.
2. [Storyful on Github](https://github.com/storyful/irish-elections), Source of .csv file for candidates.
3. [Stack Overflow](http://stackoverflow.com/questions/36519209/neo4j-graph-database-relationships/36519912#36519912), For help with Realationships between nodes.
