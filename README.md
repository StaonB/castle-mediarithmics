# castle-mediarithmics

Here's a step-by-step description of the script:

The script starts by importing the fetch function from the node-fetch library, which allows fetching the content of a URL.

The fetchURL function takes a URL as input and retrieves its content. It uses the fetch function to send a GET request to the URL, awaits the response, and parses it as JSON. If any error occurs during the process, it is caught, logged to the console, and thrown.

The exploreRoom function takes the URL of a room, along with sets of visited rooms, visited chests, and an array for storing full chests. It controls if the room has already been visited by verifying if its URL is present in the visitedRooms set. If it has been visited, a message is logged to the console.

If the room hasn't been visited, it is added to the visitedRooms set, and its details are fetched using the fetchURL function. The function then iterates over each chest URL in the room.

For each chest, it checks if the chest has already been visited by checking if its URL is present in the visitedChests set. If it has been visited, a message is logged to the console, and the iteration continues to the next chest.

If the chest hasn't been visited, it is added to the visitedChests set, and its status is fetched using the fetchURL function. If the chest status indicates that it is not empty, the chest URL is added to the fullChests array.

After processing all the chests in the room, the function recursively calls itself for each linked room URL in the current room. This allows exploring all the connected rooms of the castle.

The main function serves as the entry point of the script. It initializes the necessary variables, including the entry URL of the castle, sets for visited rooms and chests, and an array for storing full chests.

The script starts exploring the castle from the entry URL by calling the exploreRoom function with the entry URL and the initialized sets and array.

Once the exploration is complete, the script prints the number of full chests found and the locations of those chests.

Finally, the main function is called to start the script execution.

TL;DR the script fetches the content of URLs, explores rooms in a castle, checks chests in each room, and keeps track of visited rooms and chests to avoid revisiting them. The result is a list of full chests found during the exploration.
