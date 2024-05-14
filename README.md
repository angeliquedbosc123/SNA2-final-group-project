# SNA2-final-group-project
## Introduction
The UK operates on a parliamentary system and is classified as a representative democracy, which means the public elect Members of the Parliament (MPs) to represent their interest in monitoring the work of the Government. The leader of the party that has the most MPs elected after a General Election becomes the Prime Minister (PM), or the Head of Government. The Parliament is made up of three parts: the House of Commons, the House of Lords, and the Monarch. The House of Commons is the elected chamber of Parliament, where laws are debated and amended. By contrast, the House of Lords is made up of Hereditary Peers (i.e. those who inherited their noble ranks), Life Peers (i.e. those who cannot pass their title on to their children) and Bishops. The Lords are nominated by the PM and appointed by the Crown, all of whom are selected for their knowledge and expertise in order to assist the work of the House of Commons. 

Perhaps with little surprise, the lack of representativeness of the House of Lords has been subject to critique (e.g. Dorey and Purvis, 2018), as it remains a large, unelected chamber of Parliament in a representative democracy. Taking into account of this, along with recent trends in convergence of party policies in Europe (e.g. Spoon and Klüver, 2019), this project is driven by a key question on representation: representation of whom? In light of this, our group decided to map the financial interests of members in the House of Lords by their political party, and investigate whether the homogenisation of the Labour / Conservative party policies is linked to the shared financial interest among the Lords. The result of this analysis will have implications in understanding the nature of representation of the House of Lords. 

## Theoretical Framework
Our project mainly drew on Borgatti and Halgin’s (2011) work on Affiliation Networks. In social network studies, _affiliation_ refers to group membership or participation in certain events. Affiliation data consists of binary relationships between 2 sets of items, producing bipartite networks, where ties are only established between sets of nodes but not within the set. In our case, the first set of nodes would be the members of the House of Lords, and the second set would be the Lords’ financial interests. The binary relationship would be whether the Lords have a financial interest with certain corporations or not. However, an adaptation to the Affiliation Network can be useful for discovering underlying social ties within the sets. Here, the authors introduced the notion of _co-affiliation_ as ties within a set of nodes, which can be used as a proxy for latent social relationships. This could be co-membership of a group or mutual attendance of an event; in our case, it would be two Lords sharing the same financial interest. The justification is that co-affiliation either increases the likelihood of two members developing a social relationship (e.g. by increasing the frequency of seeing each other at regular events), or is an indicator of an existing relationship (e.g. because the two people are already acquainted, they would be more likely to spend more time together by joining the same group). In other words, it’s an observable measure of an otherwise unobservable metric. It should be noted that the extent to which co-affiliation is able to suggest latent or existing social relationships depends on the size of the network, since in extremely large groups, co-membership does not necessarily lead to or imply acquaintance. 

## Methodology 
Our dataset was found on the UK Parliament website under “Register of Members’ Financial Interests,” the URL link of which is cited in our References. Our first challenge was that our original dataset was very large quantity-wise, and companies overlapped in the original mapping. For example, Microsoft showed up as multiple nodes and distinct companies due subsets of the brand. Our solution was to conduct “data cleaning,” which is the process of identifying and replacing incorrect information in the results of a data set (Data Cleaning, 2023). Data cleaning was important as it can greatly skew the results of our data analysis and lead to inaccurate interpretations of the current political landscape. 

In our dataset, the Lords declared the companies with which they had financial interests, which made up the nodes in our network. Co-affiliation was found if there were ties within a set of nodes, which could mean two Lords sharing a said financial interest in the same company. The Lord with the highest degree centrality in our network is the Lord who has the most corporate shares in companies, and the corporation with highest centrality was composed of the most financial interests. The concept of betweenness centrality measures the extent to which a node lies on the shortest paths between other nodes in the network. Corporations with high betweenness centrality would be frequently invested in with other politicians that are not from the same party, for example Conservative and Labour parties. We ranked the Top 20 corporations with the highest betweenness centrality, and then with a histogram mapped how those corporations are divided between political parties. In our mapping of the dataset we paid attention to clusters, which symbolize communities of nodes that were more tightly connected to each other than to the rest of the network. Communities could represent clusters of corporations that are frequently invested in together, such as technology companies. We used the Girvan-Newman method, which is a community clustering technique which involves removing edges with the largest edge betweenness centrality (Chiang, 2021). “Edge betweenness” is the number of “shortest paths passing the edge” (Chiang, 2021), and in using this method we were able to simplify the dataset for more accurate analysis. 

## Google Colab Notebook
Here is the link to our group's Google Colab Notebook: https://colab.research.google.com/drive/1roEzQAWj2tK21sLJJ_6-5JMKx0ef5_eI?usp=sharing

## Results and Analysis 
In this section, we will show the results from our project that explore the financial networks and organizations associated with members of the House of Lords. As illustrated in the bipartite graph below, the graph is composed of numerous nodes and edges, highlighting that there is an extensive network of connections between the members of the House of Lord’s and the corporations that these members are financially interested in. The light green nodes on the graph represent the various corporations financially associated with the members of the House of Lords, while the other colors represent the diverse political party affiliations of House of Lord members. We have attached a more detailed breakdown of how we generated the graph in the Appendix. 

<img width="1294" alt="overview of bipartite network" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/7d3985a7-c7d7-4e30-b73c-2b9a20ae03f2">

### Degree Centrality
Degree centrality measures how many connections or links there are to a given node in a network. In our analysis, we measured the degree centrality for both corporations and the Lords. As depicted in the graph below, the Big Issue corporation had the highest degree centrality among the corporations, while Lord Glendonbrook CBE had the highest degree centrality among the politicians. These results indicate the Big issue corporation was the most invested in out of all the corporations, and Lord Glendonbrook CBE had the most connections or corporate share with different organizations for all of the politicians.  

<img width="1000" alt="top 1 corporate_the big issue" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/cefeb242-015d-4ca7-bcd7-130a9796d135">

<img width="1000" alt="top 1 Lord" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/3bb3aa17-1765-49fc-8dec-c6b20b5e7c54">

### Betweenness Centrality
Betweenness centrality measures “the number of times a node lies on the shortest path between other nodes,” within a social network (Disney, 2023). In our project, the  Big Issue' corporation had the highest betweenness centrality. This indicates that the Big Issue corporation is the leading corporation that connects the different members of the House of Lords together within the network, meaning that the Big Issue is the biggest “bridge” within this network. They would be frequently invested in by politicians not necessarily from the same political party. Below is a list of top 20 corporations by their betweenness centrality.

<p align="center">
    <img width="700" alt="top 20 corporates" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/af4baa77-6b54-463f-895a-73b24de4868e"> 
</p>

To visualize the result, we created two histograms to demonstrate the relationship between the top 20 corporation invested and the political party affiliation of the Lords. The first histogram represents the top 20 corporations by betweenness centrality with the breakdown of their investors’ political affiliation. The party affiliation is color-coded, revealing the distribution of party interest in these investments. The second histogram switches the independent and dependent variable, and shows the number of top 20 corporations linked to different political parties of the members of the House of Lords. For example, the members of the political party crossbench have 19 connections within the top 20 corporations, whereas the Democratic Unionist Party only has one connection.

<p align="center">
    <img width="800" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/056e2d75-3ad7-4aa7-9087-1ceb5d7a86ce">
</p>
<p align="center">
    <img align="center" width="800" src="https://github.com/angeliquedbosc123/SNA2-final-group-project/assets/167986231/ee9c2a76-0eaa-469e-ae59-ec1dc5c00d8a">
</p>

### Community Detection
We applied the Girvan Newman Community Detection algorithm, which “relies on the iterative elimination of edges that have the highest number of shortest paths between nodes passing through them” (Girvan-Newman algorithm). In other words, edges with high betweenness that cross between communities would be removed early in the process. In removing the edges one at a time, we can break the social network down and reveal the underlying, smaller communities within this network. In our project, these communities would be the clusters of corporations that overlap amongst the various politicians in our network, indicating that they tend to be more frequently invested together. This represents what corporations the House of Lord members are investing in and does not take into account the political affiliation of each politician. This enables us to strictly analyze the financial interests of members of the House of Lords and find groups formed within this network without the political party connecting these members. In our project this includes organization’s including, but not limited to, Chanel, Markham Services, and Magdalen College. 

## Conclusion
The exploration of the funding networks within the UK's political landscape, as facilitated by the dataset from the UK Parliament Members API, reveals significant insights into the dynamics of political financing and affiliations. Our analysis concentrated on delineating the top funders for major political parties, examining overlaps, and assessing how these relationships shape political actions and biases.

Firstly, we identified the top ten funders for each significant party, providing a clear picture of the primary financial backers and their potential influence. This comparative approach highlighted notable overlaps in funding sources, suggesting a complex web of interests that transcend party lines. Such overlaps are crucial for understanding how various industries and key individuals leverage financial contributions to sway political agendas across the spectrum. Regarding the structure of the networks, our findings demonstrate distinct patterns in how parties engage with their funders. While some parties show a denser concentration of funding from specific industries, others exhibit a more diversified portfolio of financial interests. This variation not only reflects the ideological and strategic differences between the parties but also underscores the sectors that might hold more sway in policy-making processes.

Our longitudinal analysis further provided a dynamic view of funding patterns over several years, revealing trends such as emerging industries becoming significant political contributors. This temporal perspective is vital for understanding the evolution of political-finance relationships and anticipating future shifts in political funding landscapes. The methodology employed, which combined advanced network analysis techniques with meticulous data handling in Google Colab, ensured a robust framework for our investigation. The analysis of betweenness centrality and community detection in our network graphs illuminated 'bridges' and distinct communities within the funding networks, offering insights into how information and influence might flow between different clusters of funders and political entities.

In conclusion, our study underscores the profound impact of financial contributions on political orientations and actions. By mapping the affiliations and assessing the interplay between different funding bodies and political parties, we not only enrich our understanding of political finance but also contribute to the broader discourse on transparency and the influence of capital in shaping political landscapes. Moving forward, continuous monitoring and analysis of these networks will be essential in fostering a more transparent and accountable political funding system.

## References
Borgatti, S. P. and Halgin, D. S. (2011). ‘Analyzing affiliation networks’, _The Sage handbook of social network analysis_, 1, pp.417-433.

Chiang, J. (2021). “Girvan–Newman - the Clustering Technique in Network Analysis.” Medium, Analytics Vidhya, 11 Oct. 2021, medium.com/analytics-vidhya/girvan-newman-the-clustering-technique-in-network-analysis-27fe6d665c92. 

“Data Cleaning: Definition, Methods and Relevance in Data Science.” DataScientest, 20 Apr. 2023, datascientest.com/en/data-cleaning-definition-methods-and-relevance-in-data-science. 

Dorey, P. and Purvis, M. (2018). ‘Representation in the Lords’, in _Exploring Parliament_, pp.244-254.

“Financial Interests.” Conflict of Interest: Division of Finance and Administration, 25 May 2022, coi.utk.edu/financial-interests/. 

“Register of Members’ Financial Interests.” UK Parliament,www.parliament.uk/mps-lords-and-offices/standards-and-financial-interests/parliamentary-commissioner-for-standards/registers-of-interests/register-of-members-financial-interests/

Spoon, J. J. and Klüver, H. (2019). ‘Party convergence and vote switching: Explaining mainstream party decline across Europe’, _European Journal of Political Research_, 58(4), pp.1021-1042.

## Appendix
### Creating the bipartite graph: 
G = nx.Graph(): This line creates an empty graph object called G using NetworkX.
### Politician nodes: 
politician_nodes = df.index.tolist(): This line assumes that df is a Pandas DataFrame and retrieves the index (i.e., the row labels) of the DataFrame, converting it into a list. This list presumably contains the names or identifiers of politicians.

G.add_nodes_from(politician_nodes, bipartite=0): This line adds nodes to the graph G. The nodes added are from the politician_nodes list. The argument bipartite=0 indicates that these nodes belong to the "0th" partition of the bipartite graph. In a bipartite graph, nodes can be divided into two disjoint sets such that edges only connect nodes from different sets. Here, the bipartite=0 attribute indicates that these nodes belong to one of the two partitions, typically referred to as the "left" or "top" partition.
### Corporation nodes: 
for politician, data in df.iterrows():: This loop iterates over each row in the DataFrame. For each iteration, politician represents the name, and data represents the row data associated with that politician.

companies = data.dropna().tolist()[1:]: This line extracts the non-null entries from the row data, excluding the first element (the politician's name), and the subsequent elements are the names of companies associated with that politician.

for company in companies:: This loop iterates over each company associated with the current politician.

company_list = company.split('¬'): This line splits the company entry into a list based on the '¬' delimiter. It seems like the company entry might contain multiple companies separated by this delimiter.

for comp in company_list:: This loop iterates over each individual company in the company_list.

G.add_node(comp, bipartite=1): This line adds a node to the graph G representing the current company. The bipartite=1 attribute indicates that this node belongs to the second partition of the bipartite graph. In a bipartite graph, nodes from different partitions represent different types of entities (in this case, politicians and companies), and edges only connect nodes from different partitions.

G.add_edge(politician, comp): This line adds an edge between the current politician node and the current company node. This edge represents an association between the politician and the company.

