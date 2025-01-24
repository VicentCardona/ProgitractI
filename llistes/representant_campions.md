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

## Load data from a file

The chart looks good! But, almost 150 nations have competed in the Olympics. To chart them, you’re going to load their data from a file. It will save a lot of typing!

![A bar chart showing the medal counts of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

**Computers and data** You’re just starting to learn how to get your computer work with data. Computers can do amazing things with the right data. And they can read more data in minutes than a human could in years. Python is one of the best programming languages there is for data. Python is what the YouTube algorithm, that picks the videos to show you, is made with.

Open the [second starter project](https://editor.raspberrypi.org/en/projects/charting-champions-second-starter). The Raspberry Pi code editor will open in another browser tab.

If you have a Raspberry Pi account, you can click **Save** to save a copy of the starter code to your library.

### Working offline

There are several `.csv` files included in this starter project that contain the data you need for your charts.

Open `medals.csv` and look at the data in it. See how each line has a team name and the number of medals they have won, separated by a comma.

![The Raspberry Pi code editor with medals file highlighted and open, displaying a list of countries and medal numbers seperated with a comma.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/medals-tab.png)

**CSV files** are Comma-Separated Values files. They contain data in rows and columns, like a table. Each line is a row, with commas separating that row’s values into columns. ![A few lines of a csv file.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/csv_sample.png)

You’ll need to turn each line of `medals.csv` into a text string and a number in Python, like in the lists you made.

Click on the `main.py` tab and add code to load the file into a variable by using `with open() as`. Then use a `for` loop to `print` each line from the variable.

The `for` loop will let you repeat code. So you will load hundreds of teams to your chart with just a few lines of code!

### Read a file with Python

main.py

```python
# Add data to the chart with open('medals.csv') as f: for line in f: print(line)
```

**Test:** Run your code and look at the text it prints out.

Notice that each line has two values, separated by commas.

![A list of text strings, printed out over many lines.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/lines.png)

**Debug:** If the code doesn’t work, make sure you have indented it under the `with` line, like in the example above.

Each string that your loop prints is made up of two pieces separated by a comma. Your `chart.add()` function needs each of those pieces as separate inputs.

The `split()` function breaks a string into a list, just like the lists you made earlier. The `split(',')` function makes a new list item every time it sees a comma.

Put a `#` in front of the code that prints `line`. This will turn that code into a comment, so Python will ignore it.

Use the `split()` method to break up each sting at a `,` and then store the first and second pieces in a new list. Then print those lists out.

main.py

```python
with open('medals.csv') as f: for line in f: #print(line) pieces = line.split(',') # Breaks the string into a list print(pieces) # Print each list
```

**Tip:** `split()` can split a string into a list around any text you want. You can split on punctuation, a letter, or even whole words.

**Test:** Run your code and look at the text it prints out. Each line should be a list with two items. You may notice that the second item has `\n` at the end. `\n` is usually invisible. It tells the computer it has reached the end of the line in a file.

![Many lists, each with two items, printed out.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/tally.png)

**Debug:** If your `pieces` are printing out as lists with only one item then check that you have `','` in the `()` of `line.split()`.

**Debug:** If you see a message about `split` being ‘not defined’, check that you have included `line.` before it.

Load your data into the chart as part of your `for` loop. `team` is a string so can be used as a label on the chart. `medal` is currently a string, but needs to be converted to a number. You can use the `int()` function to **cast** a string to a number.

main.py

```python
with open('medals.csv') as f: for line in f: #print(line) pieces = line.split(',') #print(pieces) team = pieces[0] medals = pieces[1] chart.add(team, int(medals)) # Make medals a number
```

**Tip:** You can now use `#` to turn `print(pieces)` into a comment too.

**Test:** Run your code and look at the chart it creates. Try hovering over some of the bars, or clicking on the names of teams to add and remove them from the chart.

![A bar chart showing the medal counts of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

**Debug:** If your chart is empty, check that you have `int(medals)` in your `chart.add()`.

**Debug:** If you see a message about an `IndexError`, your code is trying to get a value from a list index that doesn’t exist (e.g. `pieces[2]`). To fix this:

-   Check each of your `team` and `medals` variables to be sure you are only using `0` and `1` as indexes.
-   Check the printed `pieces` lists to be sure they have two items: `['Tonga', '1\n']`, not `['Tonga,1\n']`. If they don’t, then check that you have `','` in the `()` of `line.split()`.
-   Check you do not have a blank line at the bottom of your .csv file.

### Save your project

[](https://projects.raspberrypi.org/en/projects/charting-champions/1)[Investigate with data](https://projects.raspberrypi.org/en/projects/charting-champions/3)
## Investigate with data

Now your program can draw charts from files of data. You can use it on different files to compare their charts to see what you can learn.

![A bar chart showing the populations of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

### Who has the most medals?

Look at the chart you’ve made. The taller a bar is, the more medals that team has won. Hover the mouse over some of the tallest bars and notice which teams they belong to.

![A bar chart showing the populations of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/adjust_chart.gif)

Why might they have the most medals?

A good idea might be to look at both the population and wealth of teams, to see if there is any sort of pattern.

**Data analysis:** People have done these kinds of investigations since long before computers were invented. For example, in the 1850s, Florence Nightingale, a nurse, used charts and graphs to show the importance of disease prevention in caring for the sick. ![Florence Nightingale's chart of causes of mortality.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/nightingale.jpeg)

### Population sizes

A file, called `pop.csv`, with data on the populations of different countries, is part of the starter project. Because the data in `pop.csv` is also made up of a text string and a number, you can re-use your code with only small changes.

Change the chart title, the `width` of the chart, the file you are opening, and the category name to draw a chart based on the population data in `pop.csv`.

main.py

```python
chart = Bar(title='Population', width='600') # Add data to the chart with open('pop.csv') as f: for line in f: #print(line) pieces = line.split(',') #print(pieces) team = pieces[0] population = pieces[1] chart.add(team, int(population)) # Make population a number
```

Now run your program and look at the chart it draws.

![A bar chart showing the populations of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/pop.gif)

Hover the mouse over the biggest bars and notice which countries they belong to. Click the names of the really big ones to remove them from the chart; that will let you get a closer look at the others. Do any of the countries with lots of people have a large number of medals?

### Wealth

A file called `gdp.csv` is part of the starter project. It has data on the annual GDP of different countries. Just like with `pop.csv`, you’ll only need to make small changes to use it.

**GDP** is the Gross Domestic Product. It measures the value, in money, of everything produced in an area over a given time period. It can measure how rich an area is.

Change the chart title, the file you are opening, and the category name to draw a chart based on the GDP data in `gdp.csv`.

The `gdp.csv` file stores the GDP as decimal numbers. Update the type from `int` to `float` so that the numbers are in the correct format.

main.py

```python
chart.title = 'GDP' # Add data to the chart with open('gdp.csv') as f: for line in f: #print(line) pieces = line.split(',') #print(pieces) team = pieces[0] gdp = pieces[1] chart.add(team, float(gdp)) # Make GDP a number
```

Now run your program and look at the chart it draws.

![A bar chart showing the GDP of many nations. Information appears when the mouse hovers over a bar. Bars disappear as the names of nations are clicked.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/gdp.gif)

Hover the mouse over the biggest bars and notice which countries they belong to. Click the names of the really big ones to remove them from the chart; that will let you take a closer look at the others. Did any of the richest countries’ teams have very large numbers of medals?

### What did you find?

What did you discover by using your program to look at this data?

-   There are some signs that the number of people a team has to choose from helps it earn medals.
-   But population doesn’t explain how countries like France have so many medals. Or why India doesn’t have as many medals as China or the USA.
-   Money seems to explain more. Most of the countries that have lots of medals have high GDPs too.
-   Neither of them explains everything. There are teams that don’t follow this pattern.

### Jamaica does better than bigger and richer countries

So there’s more to what it takes to win Olympic medals than just people and money. What else might it be? What other ideas could you test, and what kind of data would you need to do so?

[](https://projects.raspberrypi.org/en/projects/charting-champions/2)[Quick quiz](https://projects.raspberrypi.org/en/projects/charting-champions/4)
## Upgrade your project

In this step, change how your chart looks, or what data it uses.

![A pie chart showing the running time of Marvel films.](https://projects-static.raspberrypi.org/projects/charting-champions/f398fe0d97a7a8fdcd3d233b684b75f2b244ce41/en/images/mcu_pie.png)

### Use a pie chart

Try using a pie chart for a different look, or to show how something is divided.

To create a pie chart instead of a bar chart, change the import from `pygal` to `Pie` instead of `Bar`. Do the same for the function you call to create `chart`.

### Use a different set of data

You can load and chart any data that’s in a `.csv` file with the program you’ve written.

**Choose:** Pick a different datafile for your project. There are two available:

-   `mcu.csv` is the runtime and gross income from the Marvel Cinematic Universe films
-   `carbon.csv` is the total (thousands of tons) and per-person (tons) carbon dioxide emissions of different countries and regions

Update the code that reads from `medals.csv` to read from your new file.

These files have more than one column of numbers. Use indexes on the `tally` list to choose which to add to your chart.

The carbon dioxide data uses numbers with decimals. To convert them from text strings, you’ll need to use `float()` instead of `int()`.

### Completed project

### Save your project
