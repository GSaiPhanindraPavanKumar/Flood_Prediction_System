# Flood Prediction System

A machine learning-based web application that predicts flood risk for any city using real-time weather data and geographical coordinates. The system uses trained models to analyze meteorological conditions and provide flood risk assessment with an intuitive web interface.

## 🌊 Features

- **Real-time Flood Prediction**: Predict flood risk based on current weather conditions
- **City-based Input**: Simply enter a city name to get predictions
- **Interactive Web Interface**: User-friendly form with real-time results
- **Weather Data Integration**: Uses HERE Geocoding API for location data
- **Multi-parameter Analysis**: Considers various weather factors:
  - Temperature
  - Maximum Temperature
  - Wind Speed
  - Cloud Cover
  - Precipitation
  - Humidity
- **Binary Classification**: Provides clear "Safe" or "Unsafe" flood risk assessment
- **Real-time Weather Fetching**: Gets current weather conditions for accurate predictions

## 🛠️ Technology Stack

- **Backend**: Flask (Python web framework)
- **Machine Learning**: scikit-learn (trained model)
- **Data Processing**: pandas, numpy
- **Model Persistence**: pickle
- **Weather API**: HERE Geocoding API
- **HTTP Requests**: requests library
- **Frontend**: HTML, CSS, JavaScript (responsive design)
- **Development**: Python 3.x

## 📁 Project Structure

```
Flood_Prediction_System/
├── application.py          # Main Flask web application
├── model.pickle            # Pre-trained flood prediction model
├── requirements.txt        # Python dependencies
├── data.csv               # Training dataset
├── data1.csv              # Additional dataset
├── final_plot.csv         # Plotting data
├── tempCodeRunnerFile.python # Temp execution file
├── static/                # CSS, JavaScript, and static assets
├── templates/             # HTML templates
│   └── predicts.html      # Main prediction interface
└── training/              # Model training and data processing
    ├── cities.csv         # City data
    ├── data_augment.py    # Data augmentation script
    ├── final_data.csv     # Processed training data
    ├── generate_plotting_data.py # Data visualization script
    ├── get_forecast.py    # Weather data fetching
    ├── mined.csv          # Mined weather data
    ├── plotting.csv       # Visualization data
    ├── prediction.py      # Prediction logic
    ├── scraper.py         # Web scraping utilities
    ├── train.py           # Model training script
    └── webScraping.py     # Additional scraping tools
```

## ⚙️ Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)
- HERE API key (for geocoding services)

### Setup Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/GSaiPhanindraPavanKumar/Flood_Prediction_System.git
   cd Flood_Prediction_System
   ```

2. **Install required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   
   Or install individually:
   ```bash
   pip install Flask==2.3.2
   pip install requests==2.32.2
   pip install scikit-learn==1.2.0
   pip install pandas==2.0.0
   pip install numpy==1.24.2
   ```

3. **Configure API Key:**
   - Obtain a HERE API key from [developer.here.com](https://developer.here.com)
   - Update the `api_key` variable in `application.py` with your key

4. **Verify model files exist:**
   - Ensure `model.pickle` is present in the root directory
   - If not, run the training scripts in the `training/` folder

## 🚀 Usage

### Running the Web Application

1. **Start the Flask server:**
   ```bash
   python application.py
   ```

2. **Access the application:**
   - Open your web browser
   - Navigate to `http://localhost:5000` or `http://127.0.0.1:5000`

3. **Make predictions:**
   - Enter the name of any city in the input field
   - Click submit to get the flood risk prediction
   - View detailed weather parameters and risk assessment

### API Endpoints

- `GET /`: Display the main prediction interface
- `GET /predicts.html`: Display the prediction form
- `POST /predicts.html`: Process city input and return flood prediction

## 🔧 Model Details

### Algorithm
- **Model Type**: Machine Learning Classifier (specific algorithm in model.pickle)
- **Input Features**: 6 weather parameters
- **Output**: Binary classification (0 = Safe, 1 = Unsafe)

### Input Parameters
1. **Temperature**: Current temperature (°C)
2. **Maximum Temperature**: Daily maximum temperature (°C)
3. **Wind Speed**: Current wind speed (km/h)
4. **Cloud Cover**: Cloud coverage percentage
5. **Precipitation**: Precipitation amount (mm)
6. **Humidity**: Relative humidity percentage

### Data Flow
1. User enters city name
2. HERE API geocodes city to get coordinates
3. Weather data fetched for the coordinates
4. Data processed and fed to the trained model
5. Model returns flood risk prediction
6. Results displayed with weather details

## 🌍 Supported Locations

- Any city with valid geocoding data from HERE API
- Global coverage for most populated areas
- Automatic coordinate extraction from city names

## 📊 Training Data

The system uses multiple CSV files for training:
- `data.csv`: Historical weather and flood data
- `data1.csv`: Additional training samples
- `final_data.csv`: Processed training dataset
- `cities.csv`: City metadata and coordinates

## 🔧 Configuration

### Server Configuration
- **Host**: 0.0.0.0 (accessible from all interfaces)
- **Port**: Configurable via PORT environment variable (default: 5000)
- **Debug Mode**: Enabled for development

### Environment Variables
- `PORT`: Server port number (optional, defaults to 5000)

## 📝 Example Usage

### Sample Input
```
City: Mumbai
```

### Expected Output
```
Information about Mumbai
Temperature: 28.5°C
Max Temperature: 32.1°C
Wind Speed: 15.2 km/h
Cloud Cover: 65%
Precipitation: 2.3 mm
Humidity: 78%
Flood Risk: Safe
```

## 🚀 Future Enhancements

- [ ] Add more sophisticated ML models (Random Forest, Neural Networks)
- [ ] Implement real-time weather API integration
- [ ] Add historical flood data visualization
- [ ] Include multiple weather data sources
- [ ] Add flood severity levels (instead of binary classification)
- [ ] Implement user location-based predictions
- [ ] Add mobile-responsive design improvements
- [ ] Include flood preparedness recommendations
- [ ] Add data export functionality
- [ ] Implement prediction confidence scores

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Add tests if applicable
5. Commit your changes (`git commit -am 'Add new feature'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Create a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**GSaiPhanindraPavanKumar**
- GitHub: [@GSaiPhanindraPavanKumar](https://github.com/GSaiPhanindraPavanKumar)

## 🙏 Acknowledgments

- HERE Technologies for geocoding services
- scikit-learn community for machine learning tools
- Flask development team for the web framework
- Open weather data providers
- Scientific community for flood prediction research

## 📞 Support

If you encounter any issues or have questions:

1. Check the existing [Issues](https://github.com/GSaiPhanindraPavanKumar/Flood_Prediction_System/issues)
2. Create a new issue with detailed description
3. Provide steps to reproduce the problem
4. Include system information and error logs

## ⚠️ Disclaimer

This application is designed for educational and research purposes. For critical flood risk decisions, please consult with meteorological experts and official weather services. The predictions should not be used as the sole basis for emergency planning or evacuation decisions.
