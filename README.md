# Satellite Ground Station Visibility Analysis

This project provides tools for visualizing satellite orbits and analyzing Line of Sight (LoS) visibility between satellites and ground stations. It uses Cesium for 3D visualization and Skyfield for accurate orbital calculations.

## Features

- 3D visualization of satellite orbits
- Ground station network visualization
- Line of Sight (LoS) analysis between satellites and ground stations
- Dynamic visibility windows calculation
- Color-coded visualization based on orbital inclinations
- Time-based animation of satellite movements and visibility

## Ground Station Network

The project includes six ground stations strategically located around the world:

| Region       | Ground Station Location  | Coordinates           |
|--------------|-------------------------|----------------------|
| US West      | Boardman, Oregon (USA)   | 45.8397° N, 119.7006° W |
| US East      | Wallops Island (USA)     | 37.9402° N, 75.4664° W  |
| Europe       | Dublin (Ireland)         | 53.3331° N, 6.2489° W   |
| Asia Pacific | Sydney (Australia)       | -33.8688° S, 151.2093° E |
| Middle East  | Bahrain                  | 26.0667° N, 50.5577° E   |
| Africa       | Cape Town (South Africa) | -33.9249° S, 18.4241° E  |

## Requirements

- Python 3.9+
- Required Python packages:
  - skyfield
  - numpy
  - json

## Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd [repository-name]
```

2. Create and activate a virtual environment:
```bash
python -m venv satenv
source satenv/bin/activate  # On Windows: satenv\Scripts\activate
```

3. Install required packages:
```bash
pip install skyfield numpy
```

## Usage

### 1. Generate Satellite Visualization

Run the script to generate the 3D satellite visualization:
```bash
python generate_czml24.py
```
This creates `czml_3d_satellites_with_models.json` containing the satellite visualization data.

### 2. Calculate Line of Sight

Calculate visibility between satellites and ground stations:
```bash
python calculate_los.py
```
This generates `visibility_data.json` with detailed visibility information.

### 3. Generate Combined Visualization

Create the integrated visualization with satellites, ground stations, and LoS:
```bash
python generate_los_visualization.py
```
This produces `combined_visualization.czml` for viewing in Cesium.

### Viewing in Cesium

1. Load the generated CZML file in Cesium:
   - Open Cesium ion
   - Upload the `combined_visualization.czml` file
   - View the visualization in the Cesium viewer

2. Visualization features:
   - Moving satellites with orbital paths
   - Ground stations with labels
   - Dynamic Line of Sight connections
   - Time controls for animation
   - Color-coded elements for easy identification

## Visualization Details

- **Satellites**:
  - 3D models with orbital paths
  - Color-coded by inclination (60° = green, 120° = cyan)
  - Labels showing satellite IDs

- **Ground Stations**:
  - Unique colors for each station
  - Clear labels with station names
  - Fixed positions on Earth's surface

- **Line of Sight**:
  - Dynamic glowing lines between stations and visible satellites
  - Color-coded to match ground stations
  - Updates based on actual visibility windows

## Time Controls

The visualization includes:
- 24-hour simulation period
- 60x time multiplier
- Play/pause controls
- Timeline for specific time selection
- Loop functionality

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

[Your chosen license]

## Acknowledgments

- Cesium for the 3D visualization platform
- Skyfield for orbital calculations
- NASA for satellite data
