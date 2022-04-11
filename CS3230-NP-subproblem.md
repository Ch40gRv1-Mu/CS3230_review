# CS3230 NP subproblem

## Clique

Given a graph G=(V,E), a clique of G is a subset $V'\subseteq V$  such that $\forall v,u \in V: uv\in E $. i.e. G'= (V', E) is a complete graph. |V'| is the size of a clique 

* Optimization version: given a graph G, find the maximum size of clique of G
* Decisional version: given a graph G and a number k. decides whether there exists clique of G with size k

#### Proof: clique is a NP-complete problem.

1. Claim: clique is a NP problem

   1.1 Given instance G=(V,E), k of the clique problem, let subset $V'\subseteq V$  be the certificate and verify it with the following algorithm:

   ​	1.1.1 Verify whether |V'| = k

   ​	1.1.2 Verify all $u,v\in V', u\neq v$:  $(u,v)\in E$

   1.2 The algorithm runs in O($|V|^2$), which is polynomia.

​	

2. Claim: clique is a NP-hard problem:

   2.1 Reduces 3-SAT to clique in polynomial:

   ​		2.1.1 Given an instance $\phi$ = $C_1 \land C_2 \land...\land C_k$, where $C_i=(l_1^i\lor l^i_2\lor l_3^i)$

   ​		2.1.2 Construct a graph G=(V,E)  in the following way:

   ​		- Each $l_j^i$  as a vertex, where $j\in \{1,2,3\}, i\in\{1,...,k\}$ 

   ​		- For any two vertices u, v, there is an edge between them if:

   ​			- They are not in the same clause(i.e. $l^i_j, l^{i'}_{j'}: i\neq i'$)

   ​			- Their values are consistent(i.e. $l^i_j, l^{i'}_{j'}: l^i_j \neq \lnot l^{i'}_{j'}$)

   ​    	2.1.3 G is an instance of vertex cover

   ​    	2.1.4 The reduction function runs in $O(3*(k-1))=O(k)$

    2.2 3-SAT returns YES $\rightarrow$ Clique returns YES:
       	2.2.1 Given that 3-SAT returns YES, there is a truth assignment to boolean variables such that $\phi$          					returns True, which implies that each clause $C_i$ will be true, and hence there must be at 					least one literal in each clause that evaluates to be true.

     	 2.2.2 Select one true literals in each clause and makes $V'\subseteq V$, and claims that $|V'|=k$  and V' is a 					clique of G, because $\forall u,v\in V'$, u,v are not from the same clause and value of u, v are both 					True, which is consistent, and therefore $(u,v)\in E$

   ​		2.2.3 Hence Clique returns YES:

   2.3 Clique returns YES $\rightarrow$ 3-SAT returns YES :

   ​		2.3.1 Given that Clique returns YES,  there exists $V'\subseteq V$  and $V'$ is Clique of G and $|V'|=k$

   ​		2.3.2 Claim: $\forall u,v \in V'$: u,v are in distinct clause. Otherwise $(u,v)\notin E$, conflicts 2.3.1

   ​		2.3.3 Claim: $\forall i\in\{1,...,k\}: \exists l^i_j \in C_i : l^i_j \in V'$, otherwise conflicts that  $|V|$

   ​		2.3.4  By assigning  each vertices in $V'$ to True, each Clause will evaluate to True and  $\phi$ will be   

   ​					evaluated to True eventually

   ​		2.3.5 Hence 3-SAT returns YES

   2.4 Hence Clique in NP-hard

   

3. Therefore Clique is NP-Complete.

​		

## Vertex cover

