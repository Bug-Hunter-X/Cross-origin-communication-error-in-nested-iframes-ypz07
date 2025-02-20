# Cross-origin communication error in nested iframes

This repository demonstrates an uncommon HTML bug related to cross-origin resource sharing (CORS) and nested iframes. The bug occurs when attempting to communicate between iframes from different origins, which browsers will often block due to security restrictions.

## Bug Description
The bug involves nested iframes loaded from different domains attempting to communicate with each other.  Directly accessing the contentWindow of another iframe is blocked unless CORS is properly configured on the originating servers.  This will result in security errors or no response.

## Solution
The solution involves using the `postMessage` API for inter-iframe communication with careful attention to the origin of the messages being sent and received.  It also requires that the target origin allows communication from the source origin.

## How to reproduce
1. Clone this repository.
2. Open `bug.html` in your browser.  
3. Observe that the attempt to communicate between frames may fail.
4. Open `bugSolution.html` to see the corrected implementation using `postMessage`.
