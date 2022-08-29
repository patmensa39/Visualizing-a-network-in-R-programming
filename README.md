# Visualizing-a-network-in-R-programming
# Visualizing a network in R programming ### 
install.packages("sna")
install.packages("igraph")
pacman::p_load(pacman, sna, igraph)

philant <- sample_gnp(n = 30, p = 0.1)
plot(philant)


### changing the edge and vertex colors 
philant <- sample_gnp(n = 30, p = 0.08)
plot(philant)

## changing the color of the vertices and edges 
philant <- sample_gnp(n = 30, p = 0.1) %>% 
  set_vertex_attr("color", value = "yellow") %>% 
  set_edge_attr("color", value = "green")
plot(philant)

### writing out a graph 
philant <- sample_gnp(n = 30, p = 0.08)
plot(philant)

write.graph(philant, file = "random_network.txt", format = "edgelist")
pdf("random_network.pdf")
plot(philant)
dev.off()
