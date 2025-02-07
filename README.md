# Data-Scimport matplotlib.pyplot as plt
import numpy as np

# Define time periods
myMonths = ["07/2019", "08/2019", "09/2019", "10/2019", "11/2019"]

# Data representation
mySearchData = [50, 53, 59, 56, 62]   # Search traffic data
myDirectData = [39, 47, 42, 51, 51]   # Direct traffic data
mySocialData = [70, 80, 90, 87, 92]   # Social media traffic data

# Set bar width and positions
myWidth = 0.25
myPositions = np.arange(len(myMonths))

# Create figure
plt.figure(figsize=(10, 6))

# Plot the bars
bars1 = plt.bar(myPositions - myWidth, mySearchData, width=myWidth, color='#1f77b4', label="Searches")
bars2 = plt.bar(myPositions, myDirectData, width=myWidth, color='#d62728', label="Direct")
bars3 = plt.bar(myPositions + myWidth, mySocialData, width=myWidth, color='#ff7f0e', label="Social Media")

# Add visitor numbers on top of the bars
for bar in bars1:
    plt.text(bar.get_x() + bar.get_width() / 2, bar.get_height(), str(bar.get_height()), 
             ha='center', va='bottom', fontsize=10)
for bar in bars2:
    plt.text(bar.get_x() + bar.get_width() / 2, bar.get_height(), str(bar.get_height()), 
             ha='center', va='bottom', fontsize=10)
for bar in bars3:
    plt.text(bar.get_x() + bar.get_width() / 2, bar.get_height(), str(bar.get_height()), 
             ha='center', va='bottom', fontsize=10)

# Customize chart labels and title
plt.xlabel("Time Periods", fontsize=12)
plt.ylabel("User Count (in thousands)", fontsize=12)
plt.title("Website Traffic Trends", fontsize=14)
plt.xticks(ticks=myPositions, labels=myMonths)
plt.legend()

# Render the visualization
plt.show()
