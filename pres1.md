## [Mint Centrality: A Centrality Measure for the Bitcoin Transaction Graph] 
 Notes by : Amandeep Singh


**[Introduction]** The paper introduces the new term Mint centrality, it discusses the introduction and needs for
the new measure. Then it explains the methodology behind the mint centrality. Which is further evaluated by doing empirical analysis. The mint centrality can be proved helpful in doing
forensics and tracing illegal activities over the bitcoin network. To calculate the mint centrality,
we need to analyze the bitcoin transactional graph. This approach gives a better approach over
previous as it is not affected much by reusing addresses and bitcoin Tumbler services which is a
service offered to mix potentially identifiable or ’tainted’ cryptocurrency funds with others, to
obscure the trail back to the fund’s source.

**[Methodology]** The methodology behind the mint centrality is that it helps in identifying the importance of
addresses. The directed acyclic graph is created from transactions of a bitcoin address. This
solution was based on the mixing of transactions from different addresses, it works by keeping
track of the coinbase transactions that an unspent transaction originates from, we can keep track
of a mixture of addresses. Mint centrality is based on the heuristic that there is also a relation between the address and the coinbase transactions that all of its UTXOs are associated with.


The vertices of the graph are used to denote bitcoin transactions and edge pointing from a
transaction using an output to a transaction creating it, so the coin base transaction won’t have
any outgoing edge. The graph generated is a Directed acyclic graph as there would be no cycles
because coinbase transactions do not depend on any transactions. Whenever a new block is created, its transactions are added to the graph. The coinbase transaction does not depend on any transactions, hence only more recent transactions can use its outputs. Other transactions use the outputs of previous
transactions, thus with every more recent transaction, at least one directed edge to an older transaction is introduced. The mint centrality can be
calculated using a sparse matrix M for all the known addresses at height h. Matrix M is updated
whenever a new block is added to the blockchain. To evaluate their proposed mint centrality
they inspected 50 addresses.

**[Empirical Analysis]** The empirical analysis on validating the proposed mint Centrality approach was done on 2000
blocks. To evaluate their proposed mint centrality they inspected 50 addresses, the results
seemed very promising as they found 18 addresses with hex value dice linked to gambling service
satoshidice, addresses having high volume transactions with gambling services, and addresses of
WikiLeaks donation address.

### Question asked in Presentation

**1. How does generating a new address to receive any return from a payment lead
to a higher mint centrality?**

The mint centrality of an address A at a given height h, is the number of distinct heights of
coinbase transactions that it can be associated with through the transaction outputs it owned
at any height before and including h. U = u1, u2, . . . , un is the set of all transactions that
created a transaction output owned by A, and n is the total number of these transactions. This
shows that if more transactions are created to receive the return from payments it will lead to
higher mint centrality.

**2. How does a node identify as an important node other than its input and output
edges?**

The node in the graph can be identified as important with other aspects of graph analysis like
Strongly Connected Component, other centrality measures like calculating Harmonic and other
approach mentioned in the paper where we calculate mint centrality.
