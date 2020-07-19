# Heap

* Tree-based with rules:
  * Parent node value >= (max heap) or <= (min heap) the value of its children

  ![Max-Heap](https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Max-Heap.svg/360px-Max-Heap.svg.png)

* Highest or lowest priority element is always stored at the root
* It's a maximally efficient implementation of a priority queue
* Insert element at bottom-right, then start swapping until it's in the correct position
