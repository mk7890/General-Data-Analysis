Geospatial visualization is a powerful way to uncover patterns in location-based data. In this guide, we’ll walk through creating interactive maps in Tableau using a dataset for Airbnb locations in Congressional Districts in New York. Whether you’re analyzing real estate trends, customer locations, or environmental data, these steps will help you bring your dataset to life.

## About the Data:

New York Airbnb dataset for Congressional District in New York (10000 rows, 12 fields (columns))

### *Dimensions;*

<mark>Id</mark> : unique numerical identification for the Airbnb location

<mark>Neighbourhood</mark>: Congressional district in New York

<mark>Room Type</mark>: either; a Shared room, Private room, Hotel room, Entire home/apartment

### *Measures;*

Availability 2020: Number of room availability in days for the year 2020

<mark>Days Occupied In 2019</mark>: Number of days occupied in 2019

<mark>F1</mark>: numerical value

<mark>Latitude</mark>: geographical latitude coordinates

<mark>Longitude</mark>: geographical longitude coordinates

<mark>Minimum Nights</mark>: least amount of nights occupied for the year

<mark>Number Of Reviews</mark>: the total number of customer reviews for the year

<mark>Price</mark>: room price per night

<mark>Reviews Per Month</mark>: the number of customer reviews per month

![Airbnb dataset Overview](https://cdn.hashnode.com/res/hashnode/image/upload/v1744226692048/c1a12aae-c4a4-4cb6-838c-5ef8ceee0075.png align="center")

## Steps:

## **1\. Connect to Your Data**

Start by importing your dataset into Tableau:

1. Open Tableau and navigate to **Connect &gt; To a File &gt; Text File** .
    
2. Select your CSV file and click **Open** .
    
3. Click **+Sheet** icon at the bottom to load the data into the workspace.
    

**Tip:** Ensure your CSV includes columns for **latitude** , **longitude** , and a geographic identifier (e.g., `neighborhood`, `city`, or `Zipcode`).

![Airbnb dataset Overview in Tableau](https://cdn.hashnode.com/res/hashnode/image/upload/v1744226750401/229b0165-4008-4c48-b530-e4e9e4aea0f1.png align="center")

![Loading data to Worksheet](https://cdn.hashnode.com/res/hashnode/image/upload/v1744226890416/da9da76a-4691-4322-82f5-e7d781d8b961.png align="center")

## **2\. Assign Geographic Roles**

Tableau needs to recognize your location data. Right-click each field in the **Data Pane** :

* **Latitude** : Assign **Geographic Role &gt; Latitude** .
    
* **Longitude** : Assign **Geographic Role &gt; Longitude** .
    
* **Neighborhood** : Assign **Geographic Role &gt; City** (or **Custom Geocoding** if your data uses non-standard names).
    

**Why?** This tells Tableau to treat these fields as spatial coordinates, enabling accurate mapping.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744227026978/ff3a3aa3-b634-42e5-9955-95eec8ff861b.png align="center")

## **3\. Create a Basic Map**

Drag fields to the **Marks Card** to build your map:

1. Drag **Latitude** to the **Rows Shelf** and **Longitude** to the **Columns Shelf** .  
    *(Tableau will auto-generate a map view.)*
    
2. Drag **Neighborhood** to the **Detail** mark.  
    *(This plots points for each neighborhood.)*
    

**Result:** A scatter plot of locations based on latitude/longitude.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744227234047/1900af69-5c8a-4f6a-b7e6-6b831a1d49b2.png align="center")

## **4\. Enhance Your Map**

Add depth by visualizing other data fields:

### **Size**

* Drag a numeric field, **price** to the **Size** mark.  
    *(Larger bubbles = higher values.)*
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744227418719/80b055d5-8aab-418d-b7fd-9f5ad40e4540.png align="center")
    

### **Color**

* Drag a categorical field, **room\_type** to the **Color** mark.  
    *(Use gradients for numbers, discrete colors for categories.)*
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744227510462/f130f2e4-d1c9-448a-b644-bfde610837ca.png align="center")
    

### **Labels & Tooltips**

* **Labels** : Drag **neighborhood** to the **Label** mark.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744227586775/3127847c-44c6-4e65-8cb6-6e91295b19e2.png align="center")
    
* **Tooltips** : Customize by clicking the **Tooltip** icon in the Marks Card. Add fields like **number\_of\_reviews** or **review\_per\_month** .
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744228049324/1ebbef74-c07a-4543-97eb-2a771cee465d.png align="center")
    
* ## **5\. Filter Your Data**
    
    Focus on specific subsets:
    
    1. **Categorical Filters** : Drag **room\_type** to the **Filters Shelf** (e.g., filter to "Entire home/apt").
        
    2. **Numeric Filters** : Drag **availability\_2020** to set thresholds (e.g., availability &gt; 100 days).
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744228835718/2a9231ed-32de-4335-ae8c-63bc5cadf431.png align="center")
        
    
    ## **6\. Customize the Map**
    
    Tailor the look and feel:
    
    1. **Background Style** : Go to **Map &gt; Map Layers** and choose **light** , **dark** , or **satellite** themes.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744230053812/31ab1ebd-e387-4356-a37b-d44a3538f5b5.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744229302036/949b8479-02b0-415b-b83a-0405593db7dd.png align="center")
        
    2. **Contextual Layers** : Enable **zip codes** , **neighborhoods** , or **city boundaries** for richer context.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744229590379/5e63b60f-ed71-4004-abf9-39293069f356.png align="center")
        
    3. **Zoom Controls** : Use the zoom slider or mouse wheel to focus on areas like Manhattan or Brooklyn.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744229898234/10d2a72e-45ff-48a8-84f5-6bb051140507.png align="center")
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744229966402/34af7433-31f7-4efc-899c-0a56d35d5c53.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1744230029243/090a8c62-6d92-43dd-bf08-d77a6b27573b.png align="center")
    
    ## **Best Practices**
    
    * **Check Geocoding Accuracy** : Verify that neighborhoods align with real-world locations.
        
    * **Optimize Performance** : For large datasets, use **Aggregation** (e.g., average price per neighborhood).
        
    * Try different combinations of size/color/labels to highlight trends.
        
    
    ## **Conclusion**
    
    With Tableau, turning raw location data into actionable insights is just a few clicks away. From identifying high-demand neighborhoods to spotting seasonal trends, maps empower you to communicate stories visually.
    
* ### **FAQ**
    
    * **Q:** What if my dataset lacks latitude/longitude?  
        **A:** Use **Custom Geocoding** or third-party tools like Google Maps API to add coordinates.
        
    * **Q:** How do I export the map?  
        **A:** Go to **Worksheet &gt; Export &gt; Image** or publish to Tableau Server/Public.
