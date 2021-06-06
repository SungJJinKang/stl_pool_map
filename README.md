# stl_pool_map
Cache friendly and Fast version of std::map

## std::map Design
When insert new item, node is newly allocated.   
Then program request heap memory(not always..) to os, This is too slow.        
And Each Node is allocated far from other nodes. This is not good for cache friendly.  

## stl_pool_map Design
Allocate multiple nodes in advance.          
Then Multiple nodes may be allocated in same cache line. This is good for performance.       
And When insert new item, stl_pool_map don't need to require memory allocation to os. It use already allocated nodes.         
And Can reuse deleted nodes.    
