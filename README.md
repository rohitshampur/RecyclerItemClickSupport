[ ![Download](https://api.bintray.com/packages/rohitshampur/maven/RecyclerItemClickSupport/images/download.svg) ](https://bintray.com/rohitshampur/maven/RecyclerItemClickSupport/_latestVersion) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-RecyclerItemClickSupport-green.svg?style=true)](https://android-arsenal.com/details/1/3268)

# RecyclerItemClickSupport



RecyclerView is a great class what you should consider over ListView for building list interfaces. It offers more flexibility and has built-in hooks that make implementing animations and custom layouts much easier compared to ListView.

Fortunately, RecyclerView supplies a addOnItemTouchListener that will catch all touch events on the item View. You can hook up a GestureDetector to figure out what happens and trigger an action from there. This has some problems as well. If you don’t implement this correctly, the GestureDetector will steal touch events and will mess up things like ripples. Also, the target view is never actually receiving the touch events in that case so your code has to emulate what happens when you click on a view to handle haptic feedback, sound effects and accessibility events.

So the solution is to let the view which is the item in your RecyclerView, or more precisely, the ViewHolder.getItemView() handle the click.

The resulting code to hook up a click listener now looks like this:

```java

ItemClickSupport.addTo(mRecyclerView).setOnItemClickListener(new ItemClickSupport.OnItemClickListener() {
    @Override
    public void onItemClicked(RecyclerView recyclerView, int position, View v) {
        // do something
    }
});
```

To use this library add below dependency to build.gradle 

```gradle

repositories{
        jcenter()
    }


dependencies {
compile 'com.rohit.recycleritemclicksupport:recycleritemclicksupport:1.0.0'
}
```

All credits goes to [Hugo Visser](https://plus.google.com/+HugoVisser/posts) and [the website](http://www.littlerobots.nl/blog/Handle-Android-RecyclerView-Clicks)

Liscensed under [Unlicense.org](http://unlicense.org/)

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>

