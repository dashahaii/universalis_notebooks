# universalis_notebooks
Uses various data to query the FFXIV Universalis API to make gil easier.

* Just hit run all in the notebook file and scroll to the end for your results. You'll need something to edit and run jupyter notebook cells.

## timed_nodes.ipynb
This takes the unspoiled (timed) gathering nodes in Eorzea and prints them into a formatted list in CSV, then it calculates the current time in Eorzea. With the list of nodes now starting at the current time in Eorzea, we do a request to Universalis' market API in a world (such as Seraph in Dynamis) to get the marketboard data for our server.

* I have this set to Seraph for now in my use case, change this to your own in the notebook.

* There are two different cells, one with and one without rarefied items. The final CSV has no rarefied items in it.

* I currently have it set to only items up to Shadowbringers due to my current game progression, you need to set this for yourself by replacing the raw text file "unpsoiled nodes" with the appropriate tables deleted from:

https://ffxiv.consolegameswiki.com/mediawiki/index.php?title=Unspoiled_Nodes&action=edit

1. First cell cleans the raw output of the webpage above, which is turned into "cleaned_nodes.csv"

2. Second cell takes all the "cleaned_nodes" and gets their nicely formatted IDs with item data using "item_ids.json", making "final_nodes_with_ids.csv"

3. Third cell calculates the time and sorts the "final_nodes_with_ids" by their active/approaching spawn time in eorzea.

4. 