# PyBer_Analysis
## Overview of Analysis
Creating an analysis of Pyber's data and putting it into a readable, easy to understand, and visually appealing presentation format helps the custumer make data driven decision on where to allocate support and resources. This analysis first involves importing Pyber's data sets into a Pandas Dataframe and the merging the two data frames together. Techniques that aid in making the data visually appealing and easy to understand include creating bubble charts that compare the average fare and the total number of rides. The bubble sizes represent the number of drivers for urban, suburban, and rural areas. The most statistical compelling figures include the mean, meadian, and mode for total number of rides for each city type, average fares for city type, and total number of drivers for each city type.
## Results

    # Build the scatter charts for each city type.
    plt.subplots(figsize=(10, 6))
    plt.scatter(urban_ride_count,
      urban_avg_fare,
      s=10*urban_driver_count, c="coral",
      edgecolor="black", linewidths=1,
      alpha=0.8, label="Urban")

    plt.scatter(suburban_ride_count,
      suburban_avg_fare,
      s=10*suburban_driver_count, c="skyblue",
      edgecolor="black", linewidths=1,
      alpha=0.8, label="Suburban")

    plt.scatter(rural_ride_count,
      rural_avg_fare,
      s=10*rural_driver_count, c="gold",
      edgecolor="black", linewidths=1,
      alpha=0.8, label="Rural")

    # Incorporate the other graph properties
    plt.title("PyBer Ride-Sharing Data (2019)", fontsize=20)
    plt.ylabel("Average Fare ($)", fontsize=12)
    plt.xlabel("Total Number of Rides (Per City)", fontsize=12)
    plt.grid(True)

    # Create a legend
    lgnd = plt.legend(fontsize="12", mode="Expanded",
         scatterpoints=1, loc="best", title="City Types")
    lgnd.legendHandles[0]._sizes = [75]
    lgnd.legendHandles[1]._sizes = [75]
    lgnd.legendHandles[2]._sizes = [75]
    lgnd.get_title().set_fontsize(12)

    # Incorporate a text label about circle size.
    plt.text(42, 35, "Note: Circle size correlates with driver count per city.", fontsize="12")


    # Save the figure.
    plt.savefig("analysis/Fig1.png")

    # Show the plot
    plt.show()

![Fig1](https://user-images.githubusercontent.com/104540261/177507290-e5704b60-240e-4f23-9252-514d5d12e30d.png)

    # Import mpl to change the plot configurations using rcParams.
    import matplotlib as mpl
    # Build Pie Chart
    plt.subplots(figsize=(10, 6))
    plt.pie(type_percents,
    labels=["Rural", "Suburban", "Urban"],
    colors=["gold", "lightskyblue", "lightcoral"],
    explode=[0, 0, 0.1],
    autopct='%1.1f%%',
    shadow=True, startangle=150)
    plt.title("% of Total Fares by City Type")
    # Change the default font size from 10 to 14.
    mpl.rcParams['font.size'] = 14
    # Save Figure
    plt.savefig("analysis/Fig5.png")
    # Show Figure
    plt.show()

![Fig5](https://user-images.githubusercontent.com/104540261/177507350-c790058c-1aef-4af1-92d2-8f700f63540f.png)

    # Build percentage of rides by city type pie chart.
    plt.subplots(figsize=(10, 6))
    plt.pie(ride_percents,
    labels=["Rural", "Suburban", "Urban"],
    colors=["gold", "lightskyblue", "lightcoral"],
    explode=[0, 0, 0.1],
    autopct='%1.1f%%',
    shadow=True, startangle=150)
    plt.title("% of Total Rides by City Type")
    # Change the default font size from 10 to 14.
    mpl.rcParams['font.size'] = 14
    # Save Figure
    plt.savefig("analysis/Fig6.png")
    # Show Figure
    plt.show()


![Fig6](https://user-images.githubusercontent.com/104540261/177507401-b6c185ae-8901-4b14-ba3f-14066af1716d.png)

    import matplotlib.dates as mdates

    # Import the style from Matplotlib.
    from matplotlib import style
    # Use the graph style fivethirtyeight.
    style.use('fivethirtyeight')

    fig, ax = plt.subplots(figsize=(15, 6))
    ax.plot(jan_apr_fare_per_week)
    ax.set_ylabel('Fare ($USD)',fontsize=14)
    ax.set_xticks(pd.date_range(start = "2019-01-01", end = "2019-04-30", freq="MS"))
    ax.set_title("Total Fare by City Type")
    # Make ticks on occurrences of each month:
    ax.xaxis.set_major_locator(mdates.MonthLocator())
    # Get only the month to show in the x-axis:
    ax.xaxis.set_major_formatter(mdates.DateFormatter('%b'))
    ax.legend(["Rural","Suburban","Urban"])
    # Import the style from Matplotlib.
    from matplotlib import style
    # Use the graph style fivethirtyeight.
    style.use('fivethirtyeight')
    # Save the figure.
    plt.savefig("PyBer_fare_summary.png")
    
![Untitled](https://user-images.githubusercontent.com/104540261/177517857-bac1750d-d60a-46b9-b233-01e32849431a.png)


![PyBer_fare_summary](https://user-images.githubusercontent.com/104540261/177510648-ef358b7b-b068-41c5-b9c4-8e8e1cd20f3d.png)
## Summary
