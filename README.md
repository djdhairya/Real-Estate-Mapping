# Real-Estate-Mapping

This project is an interactive real estate mapping tool built using **Python**, **Flask**, and **Folium**, powered by Zillow’s property dataset. The application allows users to explore properties in Texas on a map, with additional features like gross rental yield calculation and property price history retrieval.

## Features

- **Interactive Map**: Displays real estate properties in Texas with detailed information using Folium.
- **Property Details**: View key details such as price, bedrooms, bathrooms, living area, Zestimate, and Rent Zestimate.
- **Gross Rental Yield**: Calculate and visualize rental yield to assess investment potential.
- **Price History**: Fetch the historical price of a property by clicking a button on the property popup.
- **Marker Color Coding**: Visual indicators based on rental yield:
  - **Green**: High rental yield (above 8%)
  - **Orange**: Medium yield (between 5% and 8%)
  - **Red**: Low yield (below 5%)
  - **Black**: Off-market property
  - **Grey**: No rental yield data

## Tech Stack

- **Python**: Core programming language.
- **Flask**: Web framework for creating routes and serving HTML templates.
- **Folium**: Used to create interactive maps and markers.
- **Pandas & NumPy**: For data manipulation and processing.
- **Zillow API**: Fetch property data including price history.
- **Bright Data API**: To retrieve snapshots of historical property data.

## Installation

### 1. Clone the Repository:
```bash
git clone https://github.com/djdhairya/real-estate-mapping.git
cd real-estate-mapping
```

### 2. Install Dependencies:
Create a virtual environment (optional but recommended) and install required packages using `requirements.txt`:
```bash
pip install -r requirements.txt
```

### 3. Prepare the Dataset:
- Ensure the Zillow dataset is in the correct format and stored in the appropriate directory (e.g., `data/Zillow properties(TX).csv`).
- Add your **Bright Data API Token** in a `TOKEN` file in the project directory.

### 4. Run the Application:
```bash
python app.py
```

The app will run on `http://localhost:5000/`.

## Usage

1. **Explore Properties**: Open the home page to view real estate properties on an interactive map.
2. **View Property Details**: Click on any property marker to view its details, including price, Zestimate, rent, and more.
3. **Check Price History**: Click the "Show Price History" button on a property popup to fetch and display historical price data for that property.
4. **Marker Colors**: Use the color coding on the map to quickly identify promising investment properties based on gross rental yield.

## Project Structure

```
├── app.py                    
├── templates/
│   ├── property_map.html      
│   └── price_history.html                         
├── data/
│   └── Zillow properties(TX).csv 
├── requirements.txt           
└── README.md                  
```

## How It Works

### 1. Data Loading and Cleaning:
- The Zillow dataset is loaded using `Pandas` and cleaned to remove properties without latitude and longitude.
- Fields like price, Zestimate, Rent Zestimate, etc., are converted to numeric values, and **gross rental yield** is calculated for each property.

### 2. Map Rendering:
- **Folium** is used to generate an interactive map centered on the average location of the properties.
- **MarkerCluster** groups properties by proximity, with individual markers containing a popup with detailed property information.

### 3. Price History Retrieval:
- A dynamic button in the property popup fetches price history data using the **Bright Data API**.
- The API returns a snapshot of historical price data, which is displayed in a table format.

### 4. Marker Color Logic:
- The color of each marker is determined by the property's gross rental yield:
  - **Green** for yields above 8%
  - **Orange** for yields between 5% and 8%
  - **Red** for yields below 5%
  - **Black** for off-market properties
  - **Grey** if yield data is unavailable

## Future Improvements

- **Search Functionality**: Allow users to search for properties by price range, number of bedrooms, etc.
- **Expand Dataset**: Include more states or cities beyond Texas.
- **Graphical Price History**: Implement graphical representation of price history using libraries like Plotly or Matplotlib.


![Screenshot 2024-10-12 114311](https://github.com/user-attachments/assets/ed315917-4ea6-4f29-933d-a8f2711cfaa9)
![Screenshot 2024-10-12 114156](https://github.com/user-attachments/assets/9f46feff-711e-4b4c-bfca-29bee2551667)
![Screenshot 2024-10-12 114222](https://github.com/user-attachments/assets/eb1fa715-e808-471a-9150-006e7f59232d)





