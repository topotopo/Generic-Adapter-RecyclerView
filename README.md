# Common RecyclerView Adapter

* Create a list of different views with its different or the same set of data to bind without the boilerplate code in the RecyclerView Adapter.
* Use a single adapter for all the recyclerviews in your app.
* Current version: 1.0.1-snapshot01
* Built on top of RecyclerView, Databinding

Current version: 1.0.2

![Image of Sample App](https://github.com/topotopo/common-recyclerview-adapter-android/blob/master/screenshot.png)

## Setup
In your project’s root build.gradle, check if JCenter repository is added.
```
buildscript {
    repositories {
        jcenter()     
    }
}
```

In your app's build.gradle, add the dependency.
```
implementation 'com.mmicu.commonadapter:commonadapter:1.0.1-snapshot01'
```

## Quick Start

### Create a CommonItemHolder for every view type.
```
data class StatusFeedItemHolder(
    override var data: StatusModel?,
    override var layoutId: Int = R.layout.item_feed_status,
    override var variableId: Int?
) : CommonItemHolder<StatusModel>
```

### Extend CommonRecyclerViewAdapter.
```
class AppRecyclerViewAdapter(
    listCommonHolder: MutableList<CommonItemHolder<*>>
) : CommonRecyclerViewAdapter(listCommonHolder)
```

### Initialise the adapter.
```
private val sampleMovieList = mutableListOf<CommonItemHolder<*>>()
private lateinit var recyclerViewAdapter: CommonRecyclerViewAdapter

recyclerViewAdapter = AppRecyclerViewAdapter(
            sampleMovieList
        )
```

### Optional: Add item click listener.
```
 recyclerViewAdapter.setItemClickListener { pos, data, view ->
            //Code here
        }
```

## License
```
 Apache License
 Version 2.0, January 2004
 http://www.apache.org/licenses/
```

## Authors
```Maxine Micu, maxine.micu@gmail.com```
