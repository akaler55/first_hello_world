## [BiVA: Bitcoin Network Visualization Analysis]
Notes by : Amandeep Singh

**[Introduction and architecture overview]** The paper introduces the new graph mining tool. It discusses the introduction and background
of the bitcoin network, it’s pseudo-anonymous nature, public ledger, mixing of transactions, and
how it is difficult to follow those transactions. The paper discusses the system architecture of
BiVa and it analyzes the Ashley Madison Data breach blackmailers addresses to track the flow
of bitcoins and to find related addresses to those blackmailers. The paper shows the system
architecture of the tool which consists of front-end, back-end and web interface. It gives options
like s data exploration, visualization of subgraphs around nodes of interest, and integrates both
standard and new algorithms, including a general algorithm for flow based clustering for directed
graphs, and other Bitcoin network-specific wallet address aggregation mechanisms.

**[Graph]** A heterogeneous graph is built for the tool which has addresses and transactions as nodes and
relationships between those as edges. The paper explains the bitcoin transaction and network
characteristics, different networks that can be extracted from bitcoin data for example transaction only network, an input-output network, bitcoin address network. Then paper proceeds
on explaining the system architecture of BiVA. The bitcoin data were parsed and stored in the
Neo4j graph database management system, data was labelled with 2 different labels for transactions and addresses and relationships are labelled as input or output.

**[Implementation]** The front end of BiVA is built on python and the user interface is on Jupyter notebook. Three
main parts of the tool are data storage in Neo4j, data pre-processing using python, and netowrkx for graphs. BiVA implements methods and algorithms using Entropy centrality for the
importance of node, address aggregation based on path confluence which uses a tweaked model
of BreadthFirst Search. Another capability of the tool is to trace the transaction amount for a
given set of addresses.

For the exploration purposes tool supports the visualization of standard queries on the Bitcoin
network and it can filter the edges by setting the threshold on the value of bitcoins to find the
addresses of interest. BiVa evaluation was done by doing forensics on transactions and addresses
of Ashley Madison data-breach blackmailers. They were able to find important addresses and
transactions done by blackmailers to transfer funds or accumulate funds.

### Question asked in Presentation

**1. How suspected nodes verified?**

The authors got the suspected nodes from the blog which mentioned addresses and details of
blackmailers with blackmailing amount to 1.05 bitcoins. Those addresses with all the addresses
in distance up to 5 were aggregated, they found in subgraph transactions in an undirected manner. The results were examined using the subgraph mentioned in Fig. 7(b) in the paper which
had 4571 nodes and 4762 directed edges, and 23 of the aforementioned suspected nodes.

**2. Why suspicious addresses are important?**

The suspicious addresses are important because the bitcoin network is very big and strongly
connected so you cannot look in the complete network’s graph to find malicious addresses it is
not practically possible. So having a set of suspicious addresses gives the user a specific part
of the network with neighbors up to a certain distance to look into in form of subgraphs as we
don’t need a complete graph for analyzing some nodes.
