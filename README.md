# Scroll-tabbar-list

Create a tabBar  that sync with a widget scroll in flutter

![ezgif com-gif-maker](https://user-images.githubusercontent.com/53479736/212892405-d167edc9-ab07-4017-b56f-212720a7c9ec.gif)


dependencies:
    scrollable_list_tab_scroller: <latest>


Then we use ScrollableListTabScroller and create ui.


ScrollableListTabScroller(
  tabBuilder: (BuildContext context, int scrollIndex, bool active) =>
      Padding(
    padding: const EdgeInsets.symmetric(horizontal: 10),
    child: Text(
      product.elementAt(scrollIndex).title,
      style: !active
          ? null
          : const TextStyle(
              fontWeight: FontWeight.bold, color: Colors.green),
    ),
  ),
  itemCount: product.length,
  itemBuilder: (BuildContext context, int scrollIndex) => Column(
    crossAxisAlignment: CrossAxisAlignment.start,
    children: [
      Padding(
        padding: const EdgeInsets.symmetric(horizontal: 10.0),
        child: Text(
          product.elementAt(scrollIndex).title,
          style:
              const TextStyle(fontWeight: FontWeight.bold, fontSize: 20),
        ),
      ),
      SizedBox(
        height: 320,
        child: ListView.builder(
          itemCount: product[scrollIndex].productData.length,
          scrollDirection: Axis.horizontal,
          itemBuilder: (BuildContext context, int index) {
            print('+++${product[scrollIndex].productData.length}');
            return Container(
              color: Colors.black,
              margin: const EdgeInsets.all(10),
              child: Center(
                child: Text(
                  "ProductData ${product[scrollIndex].productData[index].productName}",
                  style:
                      const TextStyle(color: Colors.white, fontSize: 20),
                ),
              ),
            );
          },
        ),
      ),
    ],
  ),
)
