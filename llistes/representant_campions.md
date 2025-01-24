## You will make

Discover the power of lists in Python by creating an interactive chart of Olympic medals.

**The Olympic Games** began in 1896: thousands of athletes represent hundreds of nations from around the world. The modern games were inspired by ancient contests held in Olympia, Greece.

You will:

-   Use **lists** to store related data
-   Create a **chart** using the `pygal` library
-   Load data by having your program **read a file**

### Play ▶️

Run the program to load the chart. Notice that the chart is interactive. What happens when you click on the top three nations in the key on the left?

## Make a chart

Create a chart and some lists of data to display on it.

![A bar chart showing the medals won by the United States, Great Britain, and France.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list.png)

Open the [Charting champions starter project](https://editor.raspberrypi.org/en/projects/charting-champions-starter). The Raspberry Pi code editor will open in another browser tab.

If you have a Raspberry Pi account, you can click **Save** to save a copy of the starter code to your library.

If you are not using the code editor in your browser, you will need to download the project files and you may need to install `pygal` before you can import it.

### Offline project files

### Installing pygal

The starter project already has some code to import the `pygal` library, which you will use to draw your chart.

main.py

```python
from pygal import bar
```

### Make a chart

Find the `# Create a chart` comment and add code below it to make a bar chart called `chart`, inside the brackets give your chart a title.

main.py

```python
# Create a chart chart = Bar(title='Olympic medals')
```

Call `chart.render()` to display the chart.

main.py

```python
# Display the chart chart.render()
```

**Test:** Run your code to see the chart. It will be empty because it doesn’t have data yet.

![The words 'Olympic medals' on a black background.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/empty_chart.png)

**Debug**: If you see an error about `Bar()` or `chart.render()` being `not defined`:

-   If the error is for `Bar()`, make sure it has an uppercase B at the start, and brackets at the end
-   If the error is for `chart.render()`, check that it has the `.` between `chart` and `render`, as well as the brackets at the end

**Debug**: If you are not using the Raspberry Pi code editor, and the graph hasn’t appeared when you run your code, replace `chart.render()` with `chart.render_in_browser()`.

### Add some data

Python can store related data as a **list**. You can create lists by using square brackets `[]`. Items in a list are separated with commas.

Create three lists of data to show on your chart.

Each list will store a nation’s name and the number of medals won by that nation.

main.py

```python
# Add data to the chart us = ['United States', 2399] gb = ['Great Britain', 1304] fr = ['France', 751]
```

When you store something in a list, it gets an **index**. An index is a number that tells you an item’s position in a list. List indexes start from `0`, instead of `1`.

You can get an item from a list by its index. For example, `my_list[3]` will get the **fourth** item in `my_list`, because indexes start at `0`.

Use the indexes of your lists and `chart.add()` to display your data. The nation’s name at item 0 will be used as a category label for the chart and the amount of medals at item 1 will determine the height of the bar.

main.py

```python
gb = ['Great Britain', 1304] chart.add(us[0], us[1]) chart.add(gb[0], gb[1]) chart.add(fr[0], fr[1])
```

**Test:** Run your code to see the chart.

![A bar chart showing the medals won by the United States, Russia, and Great Britain.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list.png)

**Debug**: If you see a message about an `IndexError`, your code is trying to get a value from a list index that doesn’t exist (e.g. `us[2]`). To fix this:

-   Check each of your `chart.add` lines to be sure you are only using `0` and `1` as indexes.
-   Check the lines where you created your lists. Make sure each list has two items, separated by a comma.

Now load two more teams by adding new lists and `chart.add()` calls.

main.py

```python
# Add data to the chart us = ['United States', 2399] gb = ['Great Britain', 1304] fr = ['France', 751] ge = ['Germany', 655] ch = ['China', 636] chart.add(us[0], us[1]) chart.add(gb[0], gb[1]) chart.add(fr[0], fr[1]) chart.add(ge[0], ge[1]) chart.add(ch[0], ch[1])
```

**Test:** Run your code to see the updated chart. Try clicking on the United States’ name. Then watch the scale of the chart change.

![A bar chart showing the medals won by the United States, Great Britain, France, Germany, and China. When the United States' name is clicked, the tallest bar vanishes from the chart, which resizes.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/short_list_2.gif)

**Debug**: If you see a message about an `IndexError`, your code is trying to get a value from a list index that doesn’t exist (e.g. `fr[2]`). To fix this:

-   Check each of your `chart.add` lines to be sure you are only using `0` and `1` as indexes.
-   Check the lines where you created your lists. Make sure each list has two items, separated by a comma.

### Save your project

[](https://projects.raspberrypi.org/en/projects/charting-champions/0)[Load data from a file](https://projects.raspberrypi.org/en/projects/charting-champions/2)
