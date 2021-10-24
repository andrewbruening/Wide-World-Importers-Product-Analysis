# Wide-World-Importers-Product-Analysis



### Hey! I'm Andrew. Welcome to my [Github] 👋

- 📊 Data visualization is my forte. See my [Tableau] page! 
- 🚀 Most of what you see here is Tableau, Python, and Figma
- 🧠 I'm interested in how our social climate and media trends influence marketing needs
- ⛳ A nice quote: "If it's worth doing, it's worth doing well"

## Wide World Importers
**WWI is a wholesale novelty goods importer and distributor operating from the San Francisco bay area**
 
 ![](Dashboard_Screenshots/pages_gif.gif)
 Here's a link to the SQL [database] from Microsoft

This readme includes various screenshots, but you can view the actual dashboard [here]


## Approach
1. The pyodbc package was used to connect to the WWI database and query via python. 
2. First, SQL was used to create the **'productdf'** dataframe which detailed qualitative and quantitative data at the granularity level of Stock Item ID. We'd like to see a breakdown of sales success per category>subcategory>product>size/color.
3. Next, SQL was then used to create **'timedf'** which will compare transformations of revenue and profit over time.
4. Regex was implemented to standardize StockItemName in **'productdf'**, and to categorize it in **'timedf'**.
5. And finally, the two dataframes were imported to Tableau for dashboard creation.

![](Dashboard_Screenshots/tooltip_gif.gif)
## Dashboard Highlights

**The Platform/Genre Bar Graph** 
![](Dashboard_Screenshots/platform_bar_gif.gif)
- This graph was achieved with a combined field (platform & genre) bar graph on a dual axis with a shapes graph (the controller icons)
- Each shade of blue details a different genre within each platform, ordered by # of sales. 
- Tooltips can be accessed by hovering. Controller icons display similar platform stats (excluding genres)
- Parameters can then be used to filter the data by Release Year or Region. Nearly every graph and table in the dashboard can be filtered by these parameters.

**Overlapping Circle Viz** 
![](Dashboard_Screenshots/overlappingcircles_16x9_2.png)
- Visualizations like this can be made in Tableau with an intricate tweaking of calculated fields. For example, here's a window into my columns and rows pills:
 
    **Columns:** SIN([Index -1]\*PI()/180)\*[TC Value]
     
    **Rows:** COS([Index -1]\*PI()/180)\*([TC Value])+([TC Value])
     
- While there are many things that Tableau *can* be used for, some things are better off created in another program like Figma. The overlapping circle graph is one of those things. Building it in Tableau was less than intuitive, but it's important to note that the circles **are** proportional to each subgroup's sales totals.
- In conclusion, tackling juxtaposition with this type of visualization turned out to be a great choice. I'm very satisfied with the result.

**Publisher Bubble Chart**
![](Dashboard_Screenshots/publishers_gif.gif)
The most successful Publishers found their niches within specific genres and were able to corner a large portion of the market by doing so. We know that Nintendo is world-famous for their first-party platformer franchise (Mario), and EA has been the go-to for sports games for many years (FIFA, Madden). How do Publishers' #1 genres compare to their priorities?


## Data Insights

- **New products; new priorities:** 
    In 2016, we added 8 new products in a brand new Candy category. We may need to reconsider how we chose to allocate our resources.

    It's likely that our ad spend, human resources, and social media efforts were redistributed to promote this new array of products. As proven by our steep decline (see Line Graph), our current arrangement is unsustainable.

    Is the new Candy category spreading our resources too thin?

    Profit per product can be seen in this box plot to evaluate the efficacy of the Candy category as a whole. A higher concentration of points near the LQ is not a great indication for the success of these products, but more data points would be necessary to reach a more accurate conclusion.



- **Deep Pockets:** The hyper-portable Nintendo DS became the perfect addition to Japan's on-the-go pedestrian communities, made-official by its status as their most successful platform. *(see Subgroups)*

- **Franchise Families:** Mario, Pokémon, Call of Duty, and Grand Theft Auto have all become household names. These franchises have transcended generations for decades, and are largely responsible for the success of their platforms. *(see Subgroups)*

- **Publisher Priorities:** The top 3 publishers (Nintendo, EA, Activition) dominated the markets for their own respective genres (Platformer, Sports, Shooter). Each of these genres became each publisher's #1 genre by a longshot. *(see Publishers)*

- **The Shift in Shooters:** The steep upward trend in the Shooter  genre is consistent across all regions and spans multiple decades, until decreasing steadily around the late 2010s. Upon closer inspection, this downward trend is apparent across all genres. Can we consider it to be a limitation of our dataset, lacking a breadth of titles in more recent years, or is it an accurate depiction of the gaming industry as a whole? *(see Regions)*

### Looking Back

- 'games' was over twice the size of 'steam', but had much less integrity (NaN %, inconsistent Title formatting)
- 'steam' was pleasant to work with, and was prioritized for its sales data
- To avoid disturbing the accuracy of global rankings, I decided against dropping biggames titles with NaN Publisher values
- The amount of overlap between 'games' and 'steam' was almost negligible, and had I discerned that early on in the project, I may not have approached the datasets with the regex and merges in the way that I did -- Noted!

### Moving Forward

These datasets didn't include the measures necessary for a financial analysis. In the future, I'd like to work with a dataset that provides insight into how publishers prioritize budgets for certain franchises with regards to their profit margins. With the proper data, I'd like to see tiered lists for publishers and their respective franchises. 

Nintendo's Tier 1 would surely include the Mario franchise. How would other franchises like Kirby, Metroid, Zelda, etc. rank?)

## See the complete interactive dashboard [here]

</details>

[Tableau]: https://public.tableau.com/app/profile/andrew.bruening
[Github]: https://github.com/andrewbruening
[here]: https://public.tableau.com/views/WideWorldImportersProductAnalysis/HomeDash?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link
[database]: https://docs.microsoft.com/en-us/sql/samples/wide-world-importers-what-is?view=sql-server-ver15