# Disease-Risk-Estimation
Risk estimation by modelling disease transmission dynamics through user updated social interactions

This program is designed for estimating risks based on social connections assumming relatively simple and idealistically equiweighted one to one transmission dynamics with the hope that the necessarry protocols (hygiende,social distancing, wearing surgical face masks,etc.) are being followed and may not be able capable to track large social gatherings or physical contacts where transmission dynamics get chaotic , making parameters assumed insignificant here dominant enough to produce a significantly different result ,  thus require more advanced and sophesticated methods.

It cannot take action, all it can do is give people information with the hope that they will take the right necessarry actions,as people should know what they are dealing with.


With all good hope, we wish that it can make some difference and avoid something unwanted from happening.



# Objective

To find the risk of a node from multiple sources given a probability mapping
 



# Algorithmic Flow:


Find all possible paths between all given sources and target(node) in a given mapping by finding all possible paths between one source and target considering a mapping without all the other sources and repeating for all the sources, logging the paths in each case.

Calculate probability from probability mapping by intersection of all edges of a path and then a union of all paths from all sources.



# Pseudocode:

    function estimate_risk(sources ,target,mapping,risk_mapping):
        
        
        
        function find_all_possible_paths(source,target,mapping):

            while all first degree connections of source have not been explored

                backtrack=True
                for vertex = all unexplored first degree connections of current
                    
                    if vertex is target
                        log path to all_possible_paths
                    else
                        backtrack=False
                        log vertex to path
                        log vertex as an exploration of current
                        current=vertex
                        break from for loop

                if backtrack is True
                    erase current from path
                    erase all explorations of current
                    backtrack current to its predecessor from path

            return all_possible_paths



         
         
         function calculate_risk(target,risk_mapping):
            
            for source in sources
                relative_mapping = mapping without all the other sources
                log find_all_possible_paths(source,target,relative_mapping) in paths

            for i from 1 to ( total number of paths):

                combo = all i path combinations of paths
                intersection = product of risks of all distinct values of combo from risk_mapping

                if i is odd
                    add intersection to risk
                else
                    subtract subtract intersection from risk


             return risk











