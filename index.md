# Dynamic Array Optimization

As a student at the SAE Institute of Geneva in the game programming section, I was tasked to implement and to optimize some of the basic features of a game engine. 

Here, I'll be presenting my work on DynArrays.

![](https://github.com/GJeannin0/Gjeannin0.github.io/blob/master/Images/array.jpg)

One problem with fixed-size arrays is that the programmer must assume a size for the array. This may lead to erroneous assumptions that can be the source of a lot of bugs. Because the maximum can be exceeded, directly causing bugs, and the array can be way bigger than needed, wasting memory.

Another problem is that the array is not expandable. Using a small size may be more efficient for the typical data, but prevents the program from running with larger data sets.

Both of these problems can be avoided by reallocating an array when it needs to expand. This is exactly what my DynArray does, let's see how it operates. 

## How does it operate?

It is declared as a pointer and has an allocator that allocates memory to it on instantiation and when it needs to expand.
The template allows for the DynArray to be used with any type of element.
And it keeps its size and capacity in memory.

```cpp
template<typename T>
	class DynArray
	{
	private:
		FreeListAllocator& allocator_;
		size_t capacity_ = 0;
		size_t size_ = 0;
		T* data_ = nullptr;
```

```cpp
data_ = (T*)(allocator_.Allocate(sizeof(T) * capacity_, alignof(T)));
data_[0] = elem;
size_++;
```
